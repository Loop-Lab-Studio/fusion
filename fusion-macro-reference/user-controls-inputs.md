# Fusion Macro Reference: User Controls and Inputs

A quick grab of the most common user controls and inputs used in DaVinci Resolve Fusion `.setting` files. 


## Section Labels

```lua
-- InstanceInput
SectionName = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "SectionName",
  Name = "SectionName",
  Page = "Controls",
  Default = 0,
},
```

```lua
-- UserControl
SectionName = {
  LINKS_Name = "SectionName",
  LBLC_NumInputs = 1,
  LINKID_DataType = "Number",
  INPID_InputControl = "LabelControl",
  LBLC_DropDownButton = true,
  INP_External = false,
  INP_Passive = true,
  INP_Default = 0,
  ICS_ControlPage = "Controls",
},
```

## Button Toggle

```lua
-- InstanceInput
ToggleName = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "ToggleName",
  Name = "ToggleName",
  Page = "Controls",
  Default = 0,
},
```

```lua
-- UserControl
ToggleName = {
  LINKS_Name = "ToggleName",
  INP_Default = 0,
  { MBTNC_AddButton = "Off" },
  { MBTNC_AddButton = "On" },
  LINKID_DataType = "Number",
  INPID_InputControl = "MultiButtonControl",
  MBTNC_ShowName = true,
  MBTNC_ShowBasicButton = true,
  MBTNC_StretchToFit = true,
  MBTNC_ShowToolTip = false,
  ICS_ControlPage = "Controls",
},
```

## Number Control

```lua
-- InstanceInput
Num_Name = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Num_Name",
  Name = "Num_Name",
  Page = "Controls",
  Default = 0.0,
},
```

```lua
-- UserControl
Num_Name = {
  LINKS_Name = "Num_Name",
  INP_Default = 0.0,
  INP_MinScale = 0.0,
  INP_MaxScale = 1.0,
  -- INP_MinAllowed = 0.0,
  -- INP_MaxAllowed = 1.0,
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  -- INP_Integer = true,
  ICS_ControlPage = "Controls",
},
```

## Number Calculation

```lua
-- Input
Num_Name = Input {
  Expression = "",
},
```

```lua
-- UserControl
Num_Name = {
  LINKS_Name = "Num_Name",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
```

## Point Control

```lua
-- InstanceInput
Point_Name = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Point_Name",
  Name = "Point_Name",
  Page = "Controls",
  DefaultX = 0.5,
  DefaultY = 0.5,
},
```

```lua
-- UserControl
Point_Name = {
  LINKS_Name = "Point_Name",
  INP_DefaultX = 0.5,
  INP_DefaultY = 0.5,
  LINKID_DataType = "Point",
  INPID_InputControl = "OffsetControl",					
  ICS_ControlPage = "Controls",
},
```

## Point Calculation

```lua
-- Input
Point_Name = Input {
  Expression = "Point()",
},
```

```lua
-- UserControl
Curve = {
  LINKS_Name = "Curve",
  LINKID_DataType = "Point",
  INPID_InputControl = "OffsetControl",					
  INP_External = false,
  INP_Passive = true,	
  ICS_ControlPage = "Controls",
},
```

## Combo Box

```lua
-- InstanceInput
Combo_Name = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Combo_Name",
  Name = "Combo_Name",
  Page = "Controls",
  Default = 0,
},
```

```lua
-- UserControl
Combo_Name = {
  LINKS_Name = "Combo_Name",
  INP_Default = 0,
  { CCS_AddString = "Option1" },
  { CCS_AddString = "Option2" },
  { CCS_AddString = "Option3" },
  LINKID_DataType = "Number",
  INPID_InputControl = "ComboControl",
  ICS_ControlPage = "Controls",
},
```
