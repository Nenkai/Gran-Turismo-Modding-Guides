# 6.2 - Adhoc Scripts

As explained in the introduction, Adhoc Scripts are responsible for roughly 99% of the gameplay logic. They can be edited, but it is a difficult process as you will have to deal with hex-editing instructions.

To begin viewing them, you can use [GTAdhocTools](https://github.com/Nenkai/GTAdhocTools) and drag any `.adc` file into it. This should output a `.ad` and `.strings` file next to the source file.

The `.ad` file can be viewed in any text editor, preferably Notepad++. In it, you will find the source code in an [Assembly](https://en.wikipedia.org/wiki/Assembly_language) form. Adhoc Scripts are generally high level, but still contains stack handling, scopes, etc. Think of it as being similar to [C#](https://en.wikipedia.org/wiki/C_Sharp_(programming_language)).

All instructions will start with three different numbers seperated by `|`'s. Lets take the following instruction as an example and lets tear it down.

     209FD|  23| 21| STATIC_DEFINE: REPLAY_MINIMUM_HDD_SPACE

* `209FD` is the **offset of the instruction** within the `.adc` file. It will point to the instruction type, which its enum is documented [here](https://github.com/Nenkai/GTAdhocTools/blob/27e40451d1ab2de8315b705e82f79c17c9cbb0b6/GTAdhocParser/AdhocCode.cs#L297).
* `23` is the **Line Number** within the non-compiled source file (used for debugging purposes)
* `21` is the **instruction number within the current scope** (i.e function, method, top-level code).
* The rest of the line is the instruction itself.

There is no compiler as of writing this, and the only way to edit the code is by hex-editing. The process itself is easy but it is mainly the scope of what you can do that is a problem. Generally, this is how it goes:
* Dissasemble the source adhoc script
* Locate a code part and instruction that you want to edit
* Copy the instruction offset.
* Open the source `.adc` file in a hex editor.
* Go to the copied offset. You will be pointed to the instruction's type, the 4 bytes before it being the instruction's line number, and the next bytes after it being the instruction data (if applicable).
* Edit the instruction data if applicable. It varies between instruction types and are all documented [here](https://github.com/Nenkai/GTAdhocTools/tree/master/GTAdhocParser/Instructions).

## Example
With that in mind, here is a basic example for editing a constant value.

    209DA|  21| 17| INT_CONST: 1024 (0x400)

Let's say you wanted to edit 1024 to 500000. You would open the `.adc` file, go to `209DA`. The number itself is located at the next four bytes (int32), where 1024 would be `00 04 00 00`. You can use the data inspector that most hex editors have (HxD, 010) to edit the value easily. After which, setting the value to 500000 should change the bytes to `20 A1 07 00`. Then you can save.

To verify that the change was made correctly, simply just dissasemble the edited file again. If no error shows up, you are good.

# Notes
Obviously there are more complex instructions and used incorrectly, can break the game loop. Depending on where it happens, the game may still continue to run. For instance, if the game crashed while in the middle of a menu, chances are the adhoc will crash and simply restart the project. However it crashes during its loading, this is essentially a softlock.

One thing to look for in Adhoc when editing :
* Any object that is not defined (aka null `nil` in adhoc) and then used is [null derefencing](https://en.wikipedia.org/wiki/Uninitialized_variable).
* Invalid operators between object types is essentially null derefencing aswell.
* [The Stack](https://en.wikipedia.org/wiki/Stack_machine). Adhoc uses it. Editing instructions that plays with the stack will certainly break as it is not fully understood either.
* Jump Instructions. You can essentially jump anywhere you want by editing the instruction target, so you can essentially also skip checks, but watch out for undefined objects aswell. 
