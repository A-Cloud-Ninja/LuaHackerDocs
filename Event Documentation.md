```lua
os.pullEvent(<filter: String>) 
--@pullEvent: Takes an optional string filter to pull various world events. --@filter: String: Optional, name of event (empty for any) 
--@return EventName:String,<varargs>
```

## Events

### key_*
#### key_up/key_down
	Requires a terminal machine, and active focus on the terminal.
	Reports keypresses.
	returns keyValue:String, isRepeat:bool
#### Example
```lua
local buffer = ""
local event,keyValue,isRepeat = os.pullEvent("key_up")
buffer = buffer..keyValue
```


### broadcast
	 requires networking on the machine, receives broadcasted messages.
	 returns message:String
#### Example
```lua
local event,message = os.pullEvent("broadcast")
term.reset()
term.write(message)
```

### use
	 Fired when a user interacts on a computer.
	 If user is emptyhanded, reports "player".
	 If use is holding an item, reports the items' name.
	 returns itemOrPlayerName:String
#### Example
```lua
local event,name = os.pullEvent("focus")
term.reset()
if name == "player" then
	term.write("Hello Player!")
else
	term.write("Ew! My PC!")
end
```
