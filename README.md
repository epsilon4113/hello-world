--[[
	Made by Crokuran
]]

local function Create(Object, Properties)
	local New = Instance.new(Object)
	for i,v in pairs(Properties) do
		New[i] = v
	end
	return New
end

local function AddCorner(GuiObject,Roundness)
	local Corner = Instance.new("UICorner")
	Corner.CornerRadius = UDim.new(Roundness,0)
	Corner.Parent = GuiObject
end

local Player = game:GetService("Players").LocalPlayer
local Mouse = Player:GetMouse()
local RemoteFolder = game.ReplicatedStorage:WaitForChild("rbxts_include")["node_modules"]["net"]["out"]["_NetManaged"]

local Gui = Create("ScreenGui",{Name="CrokUI",ResetOnSpawn=false,Parent=Player.PlayerGui})
local MainFrame = Create("Frame",{Parent=Gui,Position=UDim2.new(0.1,0,0.3,0),Size=UDim2.new(0.2,0,0.5,0),BackgroundTransparency=0.5,BackgroundColor3=Color3.fromRGB(208,208,208),BorderSizePixel=0})

local TopBar = Create("Frame",{Parent=MainFrame,Position=UDim2.new(0,0,-0.01,0),Size=UDim2.new(1,0,0.08,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,119,65),BorderSizePixel=0})
local BarBottom = Create("Frame",{Parent=TopBar,Position=UDim2.new(0,0,0.5,0),Size=UDim2.new(1,0,0.5,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,119,65),BorderSizePixel=0})
local BarLineL = Create("Frame",{Parent=TopBar,Position=UDim2.new(0,0,0.4,0),Size=UDim2.new(0.18,0,0.3,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,140,120),BorderSizePixel=0})
local BarLineR = Create("Frame",{Parent=TopBar,Position=UDim2.new(0.82,0,0.4,0),Size=UDim2.new(0.18,0,0.3,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,140,120),BorderSizePixel=0})
local BarLineM = Create("Frame",{Parent=TopBar,Position=UDim2.new(0.2,0,0.4,0),Size=UDim2.new(0.6,0,0.3,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,140,120),BorderSizePixel=0})

local KillauraButton = Create("TextButton",{Parent=MainFrame,Position=UDim2.new(0.1,0,0.125,0),Size=UDim2.new(0.4,0,0.1,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,160,97),BorderSizePixel=0,Font=Enum.Font.TitilliumWeb,Text="Killaura (Requires held sword)",TextScaled=true,TextWrapped=true,TextStrokeColor3=Color3.fromRGB(124,58,0),TextColor3=Color3.new(1,1,1),TextStrokeTransparency=0})
local SpeedButton = Create("TextButton",{Parent=MainFrame,Position=UDim2.new(0.1,0,0.275,0),Size=UDim2.new(0.4,0,0.1,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,160,97),BorderSizePixel=0,Font=Enum.Font.TitilliumWeb,Text="Speed",TextScaled=true,TextWrapped=true,TextStrokeColor3=Color3.fromRGB(124,58,0),TextColor3=Color3.new(1,1,1),TextStrokeTransparency=0})
local NukebridgeButton = Create("TextButton",{Parent=MainFrame,Position=UDim2.new(0.1,0,0.425,0),Size=UDim2.new(0.4,0,0.1,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,160,97),BorderSizePixel=0,Font=Enum.Font.TitilliumWeb,Text="Nukebridge",TextScaled=true,TextWrapped=true,TextStrokeColor3=Color3.fromRGB(124,58,0),TextColor3=Color3.new(1,1,1),TextStrokeTransparency=0})
local InstantPickButton = Create("TextButton",{Parent=MainFrame,Position=UDim2.new(0.55,0,0.275,0),Size=UDim2.new(0.4,0,0.1,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,160,97),BorderSizePixel=0,Font=Enum.Font.TitilliumWeb,Text="Instant Pickup",TextScaled=true,TextWrapped=true,TextStrokeColor3=Color3.fromRGB(124,58,0),TextColor3=Color3.new(1,1,1),TextStrokeTransparency=0})
local BuyWoolButton = Create("TextButton",{Parent=MainFrame,Position=UDim2.new(0.55,0,0.425,0),Size=UDim2.new(0.4,0,0.1,0),BackgroundTransparency=0,BackgroundColor3=Color3.fromRGB(255,160,97),BorderSizePixel=0,Font=Enum.Font.TitilliumWeb,Text="Buy Wool",TextScaled=true,TextWrapped=true,TextStrokeColor3=Color3.fromRGB(124,58,0),TextColor3=Color3.new(1,1,1),TextStrokeTransparency=0})

local ReachBox = Create("TextBox",{Parent=MainFrame,Position=UDim2.new(0.55,0,0.15,0),Size=UDim2.new(0.2,0,0.05,0),BackgroundTransparency=0,BackgroundColor3=Color3.new(1,1,1),BorderColor3=Color3.fromRGB(255,174,119),BorderSizePixel=5,Font=Enum.Font.TitilliumWeb,Text="Range: 80",TextScaled=true,TextWrapped=true,TextStrokeColor3=Color3.new(1,1,1),TextColor3=Color3.new(0,0,0),PlaceholderText="Enter range"})

local Credits = Create("TextLabel",{Parent=MainFrame,Position=UDim2.new(0.2,0,0.75,0),Size=UDim2.new(0.6,0,0.05,0),BackgroundTransparency=1,Font=Enum.Font.TitilliumWeb,Text="Made by Crokuran",TextScaled=true,TextWrapped=true,TextStrokeColor3=Color3.fromRGB(124,58,0),TextColor3=Color3.new(1,1,1),TextStrokeTransparency=0,TextYAlignment=Enum.TextYAlignment.Top})
local KeybindNote = Create("TextLabel",{Parent=MainFrame,Position=UDim2.new(0.2,0,0.76,0),Size=UDim2.new(0.6,0,0.1,0),BackgroundTransparency=1,Font=Enum.Font.TitilliumWeb,Text="Hold G to autobridge",TextScaled=true,TextWrapped=true,TextStrokeColor3=Color3.fromRGB(124,58,0),TextColor3=Color3.new(1,1,1),TextStrokeTransparency=0,TextYAlignment=Enum.TextYAlignment.Bottom})
local BlockNote = Create("TextLabel",{Parent=MainFrame,Position=UDim2.new(0,0,0.85,0),Size=UDim2.new(1,0,0.15,0),BackgroundTransparency=1,Font=Enum.Font.TitilliumWeb,Text="Blocks required (32 blocks are recommended for nukebridge)",TextScaled=true,TextWrapped=true,TextStrokeColor3=Color3.fromRGB(124,58,0),TextColor3=Color3.new(1,1,1),TextStrokeTransparency=0})

AddCorner(MainFrame, 0.05)
AddCorner(TopBar, 0.3)
AddCorner(KillauraButton, 0.1)
AddCorner(SpeedButton, 0.1)
AddCorner(NukebridgeButton, 0.1)
AddCorner(InstantPickButton, 0.1)
AddCorner(BuyWoolButton, 0.1)

local IsDark = _G.DarkMode
if IsDark then
	MainFrame.BackgroundColor3 = Color3.new(0,0,0)
	TopBar.BackgroundColor3 = Color3.new(0,0,0)
	BarBottom.BackgroundColor3 = Color3.new(0,0,0)
	BarLineL.BackgroundColor3 = Color3.fromRGB(56,56,56)
	BarLineR.BackgroundColor3 = Color3.fromRGB(56,56,56)
	BarLineM.BackgroundColor3 = Color3.fromRGB(56,56,56)
	KillauraButton.BackgroundColor3 = Color3.fromRGB(11,11,11)
	KillauraButton.TextColor3 = Color3.new(1,1,1)
	KillauraButton.TextStrokeTransparency = 1
	SpeedButton.BackgroundColor3 = Color3.fromRGB(11,11,11)
	SpeedButton.TextColor3 = Color3.new(1,1,1)
	SpeedButton.TextStrokeTransparency = 1
	NukebridgeButton.BackgroundColor3 = Color3.fromRGB(11,11,11)
	NukebridgeButton.TextColor3 = Color3.new(1,1,1)
	NukebridgeButton.TextStrokeTransparency = 1
	InstantPickButton.BackgroundColor3 = Color3.fromRGB(11,11,11)
	InstantPickButton.TextColor3 = Color3.new(1,1,1)
	InstantPickButton.TextStrokeTransparency = 1
	BuyWoolButton.BackgroundColor3 = Color3.fromRGB(11,11,11)
	BuyWoolButton.TextColor3 = Color3.new(1,1,1)
	BuyWoolButton.TextStrokeTransparency = 1
	ReachBox.BorderColor3 = Color3.fromRGB(22,22,22)
	Credits.TextStrokeColor3 = Color3.new(0,0,0)
	KeybindNote.TextStrokeColor3 = Color3.new(0,0,0)
	BlockNote.TextStrokeColor3 = Color3.new(0,0,0)
	
	local Rumia = Create("ImageLabel",{Parent=MainFrame,Position=UDim2.new(0,0,0,0),Size=UDim2.new(1,0,1,0),BackgroundTransparency=1,Image="rbxassetid://6547394128",ImageTransparency=0.95,ScaleType=Enum.ScaleType.Crop})
end

local DragSpeed = .3

local FrameStart
local MouseStart
local HeldDown = false
TopBar.InputBegan:Connect(function(Input)
	if Input.UserInputType == Enum.UserInputType.MouseButton1 then
		HeldDown = true
		FrameStart = MainFrame.Position
		MouseStart = Input.Position
		repeat
			MainFrame.Position = MainFrame.Position:Lerp(UDim2.new(FrameStart.X.Scale,FrameStart.X.Offset + (Mouse.X - MouseStart.X),FrameStart.Y.Scale,FrameStart.Y.Offset + (Mouse.Y - MouseStart.Y)), DragSpeed)
			game:GetService("RunService").RenderStepped:Wait()
		until not HeldDown
		local EndPos = {X = Mouse.X, Y = Mouse.Y}
		for i=1,50 do
			if not HeldDown then
				MainFrame.Position = MainFrame.Position:Lerp(UDim2.new(FrameStart.X.Scale,FrameStart.X.Offset + (EndPos.X - MouseStart.X),FrameStart.Y.Scale,FrameStart.Y.Offset + (EndPos.Y - MouseStart.Y)), DragSpeed)
			else
				break
			end
			game:GetService("RunService").RenderStepped:Wait()
		end
	end
end)

TopBar.InputEnded:Connect(function(Input)
	if Input.UserInputType == Enum.UserInputType.MouseButton1 then
		HeldDown = false
	end
end)

local Character = Player.Character
local KillauraActive = false
local SpeedActive = false
local NukebridgeActive = false
local InstantPickActive = false
local Range = 80

KillauraButton.MouseButton1Click:Connect(function()
	if KillauraActive then
		KillauraActive = false
		KillauraButton.Text = "Killaura"
	else
		KillauraActive = true
		KillauraButton.Text = "Killaura (Toggled)"
		repeat
			wait(.1)
			for i,v in pairs(game.Players:GetPlayers()) do
				local vchr = v.Character
				if vchr and v~=Player and v.Team~=Player.Team and Character and Character.Humanoid.Health>0 then
					local vhum = vchr:FindFirstChild("Humanoid")
					local vroot = vchr:FindFirstChild("HumanoidRootPart")
					if vhum and vroot and vhum.Health>0 and (vroot.Position-Character.HumanoidRootPart.Position).magnitude<=Range then
						RemoteFolder.SwordHit:InvokeServer({entityInstance=vchr,weapon=Character.HandInvItem.Value})
					end
				end
			end
		until not KillauraActive
	end
end)

local Con
SpeedButton.MouseButton1Click:Connect(function()
	if SpeedActive then
		SpeedActive = false
		SpeedButton.Text = "Speed"
	else
		SpeedActive = true
		SpeedButton.Text = "Speed (Toggled)"
		repeat
			wait()
			if Character and Character.Humanoid.Health>0 then
				Character.Humanoid.WalkSpeed = 30
			end
		until not SpeedActive
		Character.Humanoid.WalkSpeed = 16
	end
end)

NukebridgeButton.MouseButton1Click:Connect(function()
	if NukebridgeActive then
		NukebridgeActive = false
		NukebridgeButton.Text = "Nukebridge"
	else
		NukebridgeActive = true
		NukebridgeButton.Text = "Nukebridge (Toggled)"
	end
end)

InstantPickButton.MouseButton1Click:Connect(function()
	if InstantPickActive then
		InstantPickActive = false
		InstantPickButton.Text = "Instant Pickup"
	else
		InstantPickActive = true
		InstantPickButton.Text = "Instant Pickup (Toggled)"
		repeat
			wait()
			for i,v in pairs(workspace.ItemDrops:GetChildren()) do
				if Character and Character.Humanoid.Health>0 and (v.Position-Character.HumanoidRootPart.Position).magnitude<=10 then
					local x,y,z = math.ceil(v.Position.X/3),math.ceil(v.Position.Y/3),math.ceil(v.Position.Z/3)
					coroutine.wrap(function()
						RemoteFolder.PickupItemDrop:InvokeServer({itemDrop=v})
					end)()
				end
			end
		until not InstantPickActive
	end
end)

BuyWoolButton.MouseButton1Click:Connect(function()
	if Character and Character.Humanoid.Health>0 then
	RemoteFolder.BedwarsPurchaseItem:InvokeServer({shopItem={price=8,currency="iron",itemType="wool_white",amount=16}})
	end
end)

ReachBox.FocusLost:Connect(function(entered)
	if entered then
		if tonumber(ReachBox.Text) then
			Range = math.clamp(tonumber(ReachBox.Text),1,100)
			ReachBox.Text = "Range: ".. Range
		end
	end
end)

Player.CharacterAdded:Connect(function()
	Character = Player.Character
	Character.Humanoid.Died:Connect(function()
		Character = nil
	end)
end)

Character.Humanoid.Died:Connect(function()
	Character = nil
end)

local UIS = game:GetService("UserInputService")
local GHeld = false
UIS.InputBegan:Connect(function(Input, GSE)
	if not GSE then
		if Input.KeyCode == Enum.KeyCode.G then
			GHeld = true
			repeat
				if Character and Character.Humanoid.Health>0 then
    				if NukebridgeActive then
    					for i,v in pairs(workspace.Map.Blocks:GetChildren()) do
    						if v.Size.magnitude<=10 and (v.Position-Character.HumanoidRootPart.Position).magnitude<=20 and (v.Position-Character.HumanoidRootPart.Position).magnitude>=8 then
    							local x,y,z = math.ceil(v.Position.X/3),math.ceil(v.Position.Y/3),math.ceil(v.Position.Z/3)
    							coroutine.wrap(function()
    								RemoteFolder.BreakBlock:InvokeServer({blockRef={blockPosition=Vector3.new(x,y,z)},hitPosition=v.Position,hitNormal=Vector3.new(0,0,1)})
    							end)()
    						end
    					end
    					local pos = Character.HumanoidRootPart.Position + Character.HumanoidRootPart.Velocity*Vector3.new(1,0,1)/4
    					for o=-1,1 do
    						for i=-1,1 do
    							local x, y, z = pos.X+(i*3),pos.Y-5.5,pos.Z+(o*3)
    							coroutine.wrap(function()
    								RemoteFolder.PlaceBlock:InvokeServer({position = Vector3.new(math.ceil((x/3)-.5),math.ceil((y/3)-.5),math.ceil((z/3)-.5)),blockType = "wool_"..string.lower(Player.Team.Name)})
    							end)()
    						end
    					end
    				else
    					local pos = Character.HumanoidRootPart.Position + Character.HumanoidRootPart.Velocity*Vector3.new(1,0,1)/6
    					for o=-1,1 do
    						for i=-1,1 do
    							local x, y, z = pos.X+(i*2),pos.Y-5.5,pos.Z+(o*2)
    							coroutine.wrap(function()
    								RemoteFolder.PlaceBlock:InvokeServer({position = Vector3.new(math.ceil((x/3)-.5),math.ceil((y/3)-.5),math.ceil((z/3)-.5)),blockType = "wool_"..string.lower(Player.Team.Name)})
    							end)()
    						end
    					end
    				end
				end
				wait()
			until not GHeld
		end
	end
end)
UIS.InputEnded:Connect(function(Input)
	if Input.KeyCode == Enum.KeyCode.G then
		GHeld = false
	end
end)
