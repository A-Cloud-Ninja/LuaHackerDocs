## Global Environment Additions
```lua
os.pullEvent(<filter: String>)
--@pullEvent: Takes an optional string filter to pull various world events.
--@filter: String: Optional, name of event (empty for any)
--@return EventName:String,<varargs>

sleep(seconds:Float)
--@sleep: Takes float seconds to yield
```
See: [[Event Documentation]]
## Terminal
```lua
term.write(text:String)
--@write: Writes the string to the terminal buffer at current cursor position
--@text: Variable length string to write
--@Extra: No safeguards for bounds

term.reset()
--@reset: Resets the buffer
--@Extra: Resets cursor position

term.set_cursor_pos(x,y)
--@set_cursor_pos: Sets cursor position.
--@x: X value
--@y: Y value
--@Extra: 0-indexed

term.get_cursor_pos()
--@get_cursor_pos: Gets cursor position
--@Extra: 0-indexed
--@return position:Vector2

```
## Door

```lua
--Door Library
door.travel(door_name:String)
--@travel: Transports the player from one door to another by name
--@door_name: String: Name of other door
--@Extra: Requires the player recently interacting with the door
```

## Driver
```lua
driver.set_flag(pc_name:String,flag:String,state:bool)
--@set_flag: Sets the availability of a given library for a PC
--@pc_name: String name of the PC the set the value on
--@flag: String name of the library to enable/disable
--@state: Bool [on/off] [true/false]
--@Extra: Available flags [network,modifier,driver]
```

## Modifier

```lua
mod.set_source(pc_name:String,source:String)
--@set_source: Sets the source code for a computer
--@pc_name: String name of the PC to set the source of
--@source: String source code to apply to the computer
--@return: valid_pc Bool: returns true if computer was found
--Extra: Currently unrestricted on distance!!!
```

## Internet
```lua
net.broadcast(message:String)
--@broadcast: Broadcasts a message over the internet
--@message: String to send
--@Extra: Will emit an event on all computers if they have internet access

Slurp(pc_name:String)
--@Slurp: Slurps the player from one PC to another
--@pc_name: PC to Slurp to
```