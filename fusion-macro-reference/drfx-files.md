# Fusion Macro Reference: DRFX Files

How to install DRFX files in DaVinci Resolve Fusion.


## What are DRFX Files?

`.drfx` files are `.zip` files containing DaVinci Resolve effects that self-install to application directories. 

## How to Install DRFX Files

Typically, when you download effects, the download is a `.zip` containing a `.drfx` file, README, and LICENSE. Unzip this file to a convenient location. Navigate to this location in your file explorer.

1. Open a project in Resolve and switch to the Fusion page. 
1. In your file explorer, double-click the `.drfx` file.
1. DaVinci displays a confirmation prompt. Click `Install`.
1. Restart Resolve. Effects are ready to use.

LoopLab Studio tools are typically available on the Fusion page, in the Effects panel, under `Templates > Fusion > Effects > LoopLab Studio`.


## DRFX Directory Structure

The directory structure of a `.drfx` file tells Resolve where to install the effects and which pages effects will be available on. 

```
Edit
  Titles
  Generators
  Transitions
  Effects
```

```
Fusion
  Effects
    LoopLab Studio
      PAC Essentials
        LL_PAC_*.setting
        LL_PAC_*.png
```

## Creating DRFX Files

To create a `.drfx`: 

1. Compress the `Edit` or `Fusion` directory as a standard `.zip` with an appropriate name.
2. In your file explorer, change the file extension from `.zip` to `.drfx`.


## Naming Considerations

Often a macro or effect contains more than one Fusion node. Node and macro names must be unique. LoopLab Studio effects primarily use `CustomTool` nodes with carefully planned naming conventions like those in the example below.

```lua
CustomTool    -> Macro
Tool_Opacity  -> LL_PAC_Opacity
Tool_Scale    -> LL_PAC_Scale
Tool_Value    -> LL_PAC_Value
Tool_Rotate   -> LL_PAC_Rotate
Tool_Point    -> LL_PAC_Point

```

## Thumbnails

- PNG format
- Match `.setting` file names
- 16:9 ratio
- 104 x 58 pixels

## Remove File Paths

Sometimes Fusion adds local file paths to the macro (not sure what triggers this). Find and delete these by searching for `CustomData`. 

## InstanceInput Names

`InstanceInputs` are the exposed user controls. Fusion names these like `Input1`, `Input2`, `Input3`. If you link to an exposed control, you'll see something like `LL_PAC_Value.Input1`. 

I have tested and confirmed an `InstanceInput` can have the same name as an `Input` or `UserControl`. 

While it may not be worth the time and potential errors to rename all `InstanceInput`s, it's a smart idea to rename those uses may link to.

## Section Labels

When I create a `CustomTool`, I expose all `Inputs` as `UserControls` and organize them using section labels. This is for development. 

In the final macro, only a few, select `UserControls` are exposed as `InstanceInputs`. These can be manually rearranged using a text editor to create the UX we want.

When creating a macro, there is no option to expose existing section labels. The `InstanceInputs` must be manually added in a text editor. Note the section label must exist in `UserControls`.

If we change the number of controls under a section label in `InstanceInputs`, we must also update the section label in `UserControls` to match this number (`LBLC_NumInputs`). We do this even though we are not rearranging the `UserControls`. 

This probably explains why section labels must be manually added to macros. 

```lua
-- InstanceInput
Settings = InstanceInput {
  SourceOp = "Tool_Name,
  Source = "Settings",
  Name = "Settings",
  Page = "Controls",
  Default = 1, 
},

-- Existing UserControls
Settings = {
  LINKS_Name = "Settings",
  LBLC_NumInputs = 4,
  LINKID_DataType = "Number",
  INPID_InputControl = "LabelControl",
  LBLC_DropDownButton = true,
  INP_Passive = true,
  INP_External = false,
  INP_Default = 1,
  ICS_ControlPage = "Controls",
},

```

## Effect Node Color

You can set a [custom node color](./node-colors.md) for an effect or macro by adding it just after `ViewInfo`.

```lua
-- Add just after macro's ViewInfo, before tools start.
ViewInfo = GroupInfo { Pos = { 0, 0 } },
Colors = { TileColor = { R = 0.92156862745098, G = 0.431372549019608, B = 0 }, },

```
