<div align="center">

![Velox-4|690x198](./Images/Velox-4.png)
:floppy_disk: [Download](./Release/VeloxModule.rbxm) | :open_book: [Github](https://github.com/sfgij/Velox)
Velox is a general UI module that is perfect for making your GUI fit on all devices. Complete with features that help your GUI look the same whether it's on a Phone, Tablet, or Monitor.  
</div>
(if this gets enough attention i'll make a test game)

---
## About Velox

I made Velox, for my personal use so I can use especially with scrolling frames as they are a pain to size equally on all devices. Which is important for my game which relys heavily on them. So I decided to polish up some code and release it to the Public. I landed on the name Velox because it is latin for swift or fast, because of how much faster it helped me created my scrolling frames.

---
## Documentation

Be sure you have Velox defined:
```
local Velox = require(path.to.velox)
 ```

## Text Scaling Functions:

[details="Functions"]

 ---
The Scale Text function, scales TextSize uniformly on all devices, for example, a size 25 on your computer might be a size 14 text size on a phone. This function ensures that it properly calculates that. This function returns the text size, but it will change the size without any extra work. This function will detect if the element size has changed, so it can update the size accordingly.
[details="ScaleText"]

### Function Format:
```Velox:ScaleText(object, DeveloperAbsoluteSize, DefaultTextSize)```

### Parameter Explanation:

Object: The text object
DeveloperAbsoluteSize: The AbsoluteSize of the object (For you)
DefaultTextSize: The textsize of the object for you

### Example Code:
```
local Velox = require(path.to.velox)
local Element = script.parent.TextLabel

Velox:ScaleText(Element, Vector2.new(140,50), 25)
--[[
The above code basically says that the text by default is 25
As well as the elements AbsoluteSize on your screen it (140,50)
you can find AbsoluteSize in properties.
]]
```
[/details]
 ---
The Scale Text Once function, scales TextSize uniformly on all devices, for example, a size 25 on your computer might be a size 14 text size on a phone. This function ensures that it properly calculates that. This function returns the text size, but it will change the size without any extra work. This function will __NOT__, detect changes in size and it will only scale the text once.
[details="ScaleTextOnce"]

### Function Format:
```Velox:ScaleTextOnce(object, DeveloperAbsoluteSize, DefaultTextSize)```

### Parameter Explanation:

Object: The text object
DeveloperAbsoluteSize: The AbsoluteSize of the object (For you)
DefaultTextSize: The default TextSize of the object

### Example Code:
```
local Velox = require(path.to.velox)
local Element = script.parent.TextLabel

Velox:ScaleTextOnce(Element, Vector2.new(140,50), 25)
--[[
The above code basically says that the text by default is 25
As well as the elements AbsoluteSize on your screen it (140,50)
you can find AbsoluteSize in properties.
]]
```
[/details]
 
[/details]

## GUI Scaling Functions:
[details="Functions"]

----
The GetGuiSizeScaled function, basically returns the size of the GUI scaled in position for the user, which is good for scrolling frames that autoscale or change size.
[details="GetGuiSizeScaled"]
### Function Format:
```Velox:GetGuiSizeScaled(DeveloperAbsoluteSize, UserAbsoluteSize, ObjectSize)```

### Parameter Explanation:

DeveloperAbsoluteSize: The AbsoluteSize of the parent (for you, so it should be a constant)
UserAbsoluteSize: The AbsoluteSize of the parent (For the user)
ObjectSize: The size of the object in offset (for you)

### Example Code:
```
local Velox = require(path.to.velox)
local ElementParent = script.parent.ScrollingFrame
local Element = ElementParent.Frame

Element.Size = Utils:GetGuiSizeScaled(Vector2.new(1180,675),ElementParent.AbsoluteSize,UDim2.new(0,1180,0,200))
--[[
The above code states the ScrollingFrames/The Parent's absolute size is (1180,675)
As well as the elements Size on your screen is (0,1180,0,200)
with the middle parameter being the AbsoluteSize of the Parent/ScrollingFrame
]]
```

[/details]
---
The SizeScaleToOffset function changes the element's size from Scale to offset, returns true when done
[details="SizeScaleToOffset"]
### Function Format:
```Velox:SizeScaleToOffset(Object)```

### Parameter Explanation:

Object: the object to switch from Scale toOoffset

### Example Code:
```
local Velox = require(path.to.velox)
local Element = Script.Parent.Frame

Velox:SizeScaleToOffset(Element)
-- IDK self explanatory ig
```

[/details]
---
The SizeOffsetToScale function changes the element's size from Offset to Scale, returns true when done
[details="SizeOffsetToScale"]
### Function Format:
```Velox:SizeOffsetToScale(Object)```

### Parameter Explanation:

Object: the object to switch from Offset to Scale

### Example Code:
```
local Velox = require(path.to.velox)
local Element = Script.Parent.Frame

Velox:SizeOffsetToScale(Element)
-- IDK self explanatory ig
```

[/details]
[/details]

## Miscellaneous Functions

[details="Functions"]

This runs a callback function, whenever the selected object moves positions

[details="ObjectPositionListener"]
### Function Format:
```Velox:ObjectPositionListener(Object, Data, Callback)```

### Parameter Explanation:

Object: The object to listen for
Data: Any extra data needed (will be passed on), could be a table or anything
Callback: Function for callback the data will be passed within the function as Function(Object,Data) please plan accordingly

### Example Code:
```
local Velox = require(path.to.velox)
local Element = Script.Parent.Frame

local function Callback()
    Print("ObjectMoved")
end

Velox:ObjectPositionListener(Element, nil, Callback)

--[[
Basically prints "ObjectMoved", everytime it moves, with nil as the data
because no data is needed for this example
]]
```

[/details]

This runs a callback function, whenever the selected object changes size

[details="ObjectSizeListener"]
### Function Format:
```Velox:ObjectSizeListener(Object, Data, Callback)```

### Parameter Explanation:

Object: The object to listen for
Data: Any extra data needed (will be passed on), could be a table or anything
Callback: Function for callback the data will be passed within the function as Function(Object,Data) please plan accordingly

### Example Code:
```
local Velox = require(path.to.velox)
local Element = Script.Parent.Frame

local function Callback()
    Print("ChangedSize")
end

Velox:ObjectSizeListener(Element, nil, Callback)

--[[
Basically prints "ChangedSize", everytime it changes size, with nil as the data
because no data is needed for this example
]]
```

[/details]
[/details]

---
Made with :heart: by Sfgij




