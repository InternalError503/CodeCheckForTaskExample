Check for scheduled task example for [inno setup](https://github.com/jrsoftware/issrc) 
========

### About:
When searching the best way to check for a scheduled task in google search with [inno setup](https://github.com/jrsoftware/issrc) there was 
no real information or examples could be found so i am sharing my code, Hopefully this example will help someone.

### Example Usage:
Simply place the code example in the examples folder of [inno setup](https://github.com/jrsoftware/issrc) installation directory.


#### How to traverse tasks:
- If the task has no folder just use the task name __'TASKNAME'__
- If the task is in a folder use the folder name then backslash task name __'FOLDER\TASKNAME'__


##### Example check for a task that has no folder:
```pascal
	if (TaskExist('TASKNAME')) then
		begin
			msgbox('Your task was found!', mbInformation, MB_OK)
	end
```

##### Example check for a task that has a folder:
```pascal
	if (TaskExist('FOLDER\TASKNAME')) then
		begin
			msgbox('Your task was found!', mbInformation, MB_OK)
	end
```

##### Example check for a task that has multiple folders:
```pascal
	if (TaskExist('FOLDER\FOLDER\FOLDER\TASKNAME')) then
		begin
			msgbox('Your task was found!', mbInformation, MB_OK)
	end
```

#### Dynamic task names:
You can use `ExpandConstant()` in this field.

##### Example check for a task using `ExpandConstant()`:
```pascal
	if (TaskExist(ExpandConstant ('{#MyAppName}'))) then
		begin
			msgbox('Your task was found!', mbInformation, MB_OK)
	end
```

##### Example check for a task using multiple values in the `ExpandConstant()` field:
```pascal
	if (TaskExist(ExpandConstant ('{#MyAppName}{#MyUserInput}'))) then
		begin
			msgbox('Your task was found!', mbInformation, MB_OK)
	end
```

#### License:
Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this example code, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

THE EXAMPLE CODE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.