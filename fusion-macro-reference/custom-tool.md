# Fusion Macro Reference: Custom Tool Template

A `CustomTool` node template for DaVinci Resolve Fusion.

```lua
{
	Tools = ordered() {
		Tool_Name = Custom {
			CtrlWZoom = false,
			NameSet = true,
			Inputs = {
				LUTIn1 = Input {
					SourceOp = "Tool_NameLUTIn1",
					Source = "Value",
				},
				LUTIn2 = Input {
					SourceOp = "Tool_NameLUTIn2",
					Source = "Value",
				},
				LUTIn3 = Input {
					SourceOp = "Tool_NameLUTIn3",
					Source = "Value",
				},
				LUTIn4 = Input {
					SourceOp = "Tool_NameLUTIn4",
					Source = "Value",
				},
				ShowNumber1 = Input { Value = 0, },
				ShowNumber2 = Input { Value = 0, },
				ShowNumber3 = Input { Value = 0, },
				ShowNumber4 = Input { Value = 0, },
				ShowNumber5 = Input { Value = 0, },
				ShowNumber6 = Input { Value = 0, },
				ShowNumber7 = Input { Value = 0, },
				ShowNumber8 = Input { Value = 0, },
				ShowPoint1 = Input { Value = 0, },
				ShowPoint2 = Input { Value = 0, },
				ShowPoint3 = Input { Value = 0, },
				ShowPoint4 = Input { Value = 0, },
				ShowLUT1 = Input { Value = 0, },
				ShowLUT2 = Input { Value = 0, },
				ShowLUT3 = Input { Value = 0, },
				ShowLUT4 = Input { Value = 0, },

				-- Inputs / calculations go here.
			
			},
			ViewInfo = OperatorInfo { Pos = { 770, 16.5 } },
			UserControls = ordered() {

        -- UserControls go here.

			}
		},
		Tool_NameLUTIn1 = LUTBezier {
			KeyColorSplines = {
				[0] = {
					[0] = { 0, RH = { 0.333333333333333, 0.333333333333333 }, Flags = { Linear = true } },
					[1] = { 1, LH = { 0.666666666666667, 0.666666666666667 }, Flags = { Linear = true } }
				}
			},
			SplineColor = { Red = 255, Green = 255, Blue = 0 },
			NameSet = true,
		},
		Tool_NameLUTIn2 = LUTBezier {
			KeyColorSplines = {
				[0] = {
					[0] = { 0, RH = { 0.333333333333333, 0.333333333333333 }, Flags = { Linear = true } },
					[1] = { 1, LH = { 0.666666666666667, 0.666666666666667 }, Flags = { Linear = true } }
				}
			},
			SplineColor = { Red = 255, Green = 0, Blue = 255 },
			NameSet = true,
		},
		Tool_NameLUTIn3 = LUTBezier {
			KeyColorSplines = {
				[0] = {
					[0] = { 0, RH = { 0.333333333333333, 0.333333333333333 }, Flags = { Linear = true } },
					[1] = { 1, LH = { 0.666666666666667, 0.666666666666667 }, Flags = { Linear = true } }
				}
			},
			SplineColor = { Red = 0, Green = 180, Blue = 255 },
			NameSet = true,
		},
		Tool_NameLUTIn4 = LUTBezier {
			KeyColorSplines = {
				[0] = {
					[0] = { 0, RH = { 0.333333333333333, 0.333333333333333 }, Flags = { Linear = true } },
					[1] = { 1, LH = { 0.666666666666667, 0.666666666666667 }, Flags = { Linear = true } }
				}
			},
			SplineColor = { Red = 180, Green = 255, Blue = 0 },
			CtrlWZoom = false,
			NameSet = true,
		}
	},
	ActiveTool = "Tool_Name"
}

```
