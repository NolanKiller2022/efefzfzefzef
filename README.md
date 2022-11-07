# if game.CoreGui:FindFirstChild("MagicTrainingGui") then
	game.CoreGui.MagicTrainingGui:Destroy()
end

local Library = {}

function Library.Window(Name)
	
	local MagicTrainingGui = Instance.new("ScreenGui")
	local Main = Instance.new("Frame")
	local UICorner = Instance.new("UICorner")
	local TopBar = Instance.new("Frame")
	local UICorner_2 = Instance.new("UICorner")
	local hubName = Instance.new("TextLabel")
	local CloseFrame = Instance.new("Frame")
	local UICorner_3 = Instance.new("UICorner")
	local X = Instance.new("TextButton")
	local HideFrame = Instance.new("Frame")

	--Properties:

	MagicTrainingGui.Name = "MagicTrainingGui"
	MagicTrainingGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
	MagicTrainingGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	Main.Name = "Main"
	Main.Parent = MagicTrainingGui
	Main.BackgroundColor3 = Color3.fromRGB(53, 53, 53)
	Main.Position = UDim2.new(0.152031749, 0, 0.204119876, 0)
	Main.Size = UDim2.new(0, 430, 0, 240)

	UICorner.CornerRadius = UDim.new(0, 4)
	UICorner.Parent = Main

	TopBar.Name = "TopBar"
	TopBar.Parent = Main
	TopBar.BackgroundColor3 = Color3.fromRGB(77, 77, 77)
	TopBar.Position = UDim2.new(0.0139859933, 0, 0.0264317188, 0)
	TopBar.Size = UDim2.new(0, 417, 0, 32)

	UICorner_2.CornerRadius = UDim.new(0, 4)
	UICorner_2.Parent = TopBar

	hubName.Name = "hubName"
	hubName.Parent = TopBar
	hubName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	hubName.BackgroundTransparency = 1.000
	hubName.Size = UDim2.new(0, 376, 0, 32)
	hubName.Font = Enum.Font.Unknown
	hubName.Text = Name
	hubName.TextColor3 = Color3.fromRGB(255, 255, 255)
	hubName.TextScaled = true
	hubName.TextSize = 14.000
	hubName.TextWrapped = true
	hubName.TextXAlignment = Enum.TextXAlignment.Left

	CloseFrame.Name = "CloseFrame"
	CloseFrame.Parent = TopBar
	CloseFrame.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
	CloseFrame.Position = UDim2.new(0.916067123, 0, 0, 0)
	CloseFrame.Size = UDim2.new(0, 35, 0, 32)

	UICorner_3.CornerRadius = UDim.new(0, 4)
	UICorner_3.Parent = CloseFrame

	X.Name = "X"
	X.Parent = CloseFrame
	X.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	X.BackgroundTransparency = 1.000
	X.Size = UDim2.new(0, 35, 0, 32)
	X.Font = Enum.Font.Unknown
	X.Text = "X"
	X.TextColor3 = Color3.fromRGB(255, 255, 255)
	X.TextScaled = true
	X.TextSize = 14.000
	X.TextWrapped = true
	
	X.MouseButton1Click:Connect(function()
		MagicTrainingGui:Destroy()
	end)

	HideFrame.Name = "HideFrame"
	HideFrame.Parent = CloseFrame
	HideFrame.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
	HideFrame.BorderSizePixel = 0
	HideFrame.Size = UDim2.new(0, 6, 0, 32)

	-- Scripts:

	local function ONHFN_fake_script() -- hubName.LocalScript 
		local script = Instance.new('LocalScript', hubName)

		local Title = script.Parent
		local Plr = game.Players.LocalPlayer

		Title.MouseEnter:Connect(function()
			Title.Text = Plr.Name
		end)

		Title.MouseLeave:Connect(function()
			Title.Text = Name
		end)
	end
	coroutine.wrap(ONHFN_fake_script)()
	
end
return Library
Ui lib test
