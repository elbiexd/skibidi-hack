local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local RunService = game:GetService("RunService")
local Window = OrionLib:MakeWindow({Name = "Skibidi Hack", HidePremium = false, SaveConfig = true, ConfigFolder = "OrionTest"})

local Tab = Window:MakeTab({
	Name = "Main",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "Sonic",
	Callback = function()
		game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 100
	end    
})
Tab:AddButton({
	Name = "SuperJump",
	Callback = function()
		game.Players.LocalPlayer.Character.Humanoid.JumpPower = 100
	end    
})
Tab:AddTextbox({
	Name = "teleport",
	Default = "plr",
	TextDisappear = false,
	Callback = function(Value)
		local plr1 = game.Players.LocalPlayer
		local plr2 = game.Players:FindFirstChild(Value)

		wait(0.1)
		plr1.Character.HumanoidRootPart.CFrame = plr2.Character.HumanoidRootPart.CFrame
	end	  
})

Tab:AddButton({
	Name = "Noclip",
	Callback = function()
		local player = game.Players.LocalPlayer
		RunService.Stepped:Connect(function()
			if player.Character then
				for i,v in pairs(player.Character:GetDescendants()) do
					if v:IsA("BasePart") then
						v.CanCollide = false
					end
				end
			end
		end)
	end    
})
Tab:AddButton({
	Name = "Esp Players",
	Callback = function()
		while wait(1) do
 local camera = workspace.CurrentCamera
 local runService = game:GetService("RunService")
 local highlight = Instance.new("Highlight")
 highlight.Name = "Highlight"
 for i,v in	pairs(game.Players:GetPlayers()) do
		repeat wait() until v.Character
		if not v.Character:FindFirstChild("HumanoidRootPart"):FindFirstChild("Highlight") then
			local hclone = highlight:Clone()
			hclone.Adornee = v.Character
			hclone.Parent = v.Character.HumanoidRootPart
			hclone.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop
			hclone.Name = "Highlight"
		
		end
 end
		game.Players.PlayerAdded:Connect(function(player)
			repeat wait() until player.Character
			if not player.Character:FindFirstChild("HumanoidRootPart"):FindFirstChild("Highlight") then
				local hclone = highlight:Clone()
				hclone.Adornee = player.Character
				hclone.Parent = player.Character.HumanoidRootPart
				hclone.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop
				hclone.Name = "Highlight"

			end
		end)
		game.Players.PlayerRemoving:Connect(function(player)
			player.Character:FindFirstChild("HumanoidRootPart").Highlight:Destroy()
		end)
	 RunService.Heartbeat:Connect(function(player)
			repeat wait() until player.Character
			if not player.Character:FindFirstChild("HumanoidRootPart"):FindFirstChild("Highlight") then
				local hclone = highlight:Clone()
				hclone.Adornee = player.Character
				hclone.Parent = player.Character.HumanoidRootPart
				hclone.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop
				hclone.Name = "Highlight"
			end
	 end)
	 end
	end    
})

local Tab2 = Window:MakeTab({
	Name = "Credits",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
Tab2:AddLabel("Creator: Biefrersaucer762")

OrionLib:MakeNotification({
	Name = "Skibidi Hack",
	Content = "Bienvenido a skibid hack",
	Image = "rbxassetid://4483345998",
	Time = 5
})
