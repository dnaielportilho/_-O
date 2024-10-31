local player = game.Players.LocalPlayer 
local backpack = player.Backpack

-- Ferramenta Divine Art
local tool1 = Instance.new("Tool")
tool1.Name = "Divine Art"
tool1.RequiresHandle = true

local handle1 = Instance.new("Part")
handle1.Name = "Handle"
handle1.Size = Vector3.new(1, 1, 1)
handle1.BrickColor = BrickColor.new("Bright red")
handle1.Anchored = false
handle1.CanCollide = false
handle1.Parent = tool1

local particle1 = Instance.new("ParticleEmitter")
particle1.Color = ColorSequence.new(Color3.new(1, 0, 0))
particle1.Lifetime = NumberRange.new(1)
particle1.Rate = 100
particle1.Size = NumberSequence.new(1)
particle1.Speed = NumberRange.new(10)
particle1.Parent = handle1

tool1.Parent = backpack

tool1.Equipped:Connect(function()
    player.Character.Humanoid:EquipTool(tool1)
end)

tool1.Activated:Connect(function()
    local character = player.Character
    if character and character:FindFirstChild("Humanoid") then
        local target = game.Workspace:FindPartOnRay(Ray.new(character.HumanoidRootPart.Position, character.HumanoidRootPart.CFrame.LookVector * 10))
        
        if target and target.Parent:FindFirstChild("Humanoid") then
            local humanoid = target.Parent.Humanoid
            humanoid:TakeDamage(10)
            
            local hitEffect = Instance.new("ParticleEmitter")
            hitEffect.Color = ColorSequence.new(Color3.new(1, 1, 0))
            hitEffect.Lifetime = NumberRange.new(1)
            hitEffect.Rate = 200
            hitEffect.Size = NumberSequence.new(1)
            hitEffect.Speed = NumberRange.new(10)
            hitEffect.Parent = target
            
            delay(1, function()
                hitEffect:Destroy()
            end)
        end
    end
end)

tool1.Equipped:Connect(function()
    tool1.Handle.CFrame = player.Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, -2)
end)

-- Ferramenta True Triple Dark Blade
local tool2 = Instance.new("Tool")
tool2.Name = "True Triple Dark Blade"
tool2.RequiresHandle = true

local handle2 = Instance.new("Part")
handle2.Name = "Handle"
handle2.Size = Vector3.new(1, 5, 1)
handle2.BrickColor = BrickColor.new("Really black")
handle2.Anchored = false
handle2.CanCollide = false
handle2.Material = Enum.Material.Neon
handle2.Parent = tool2

local glow = Instance.new("ParticleEmitter")
glow.Color = ColorSequence.new(Color3.fromRGB(0, 255, 0))
glow.Lifetime = NumberRange.new(1)
glow.Rate = 100
glow.Size = NumberSequence.new(1)
glow.Speed = NumberRange.new(10)
glow.Parent = handle2

tool2.Parent = backpack

tool2.Equipped:Connect(function()
    player.Character.Humanoid:EquipTool(tool2)
end)

tool2.Activated:Connect(function()
    local character = player.Character
    if character and character:FindFirstChild("Humanoid") then
        local target = game.Workspace:FindPartOnRay(Ray.new(character.HumanoidRootPart.Position, character.HumanoidRootPart.CFrame.LookVector * 10))
        
        if target and target.Parent:FindFirstChild("Humanoid") then
            local humanoid = target.Parent.Humanoid
            humanoid:TakeDamage(20)
            
            local hitEffect = Instance.new("ParticleEmitter")
            hitEffect.Color = ColorSequence.new(Color3.fromRGB(0, 255, 0))
            hitEffect.Lifetime = NumberRange.new(1)
            hitEffect.Rate = 200
            hitEffect.Size = NumberSequence.new(2)
            hitEffect.Speed = NumberRange.new(10)
            hitEffect.Parent = target
            
            delay(1, function()
                hitEffect:Destroy()
            end)
        end
    end
end)

tool2.Equipped:Connect(function()
    tool2.Handle.CFrame = player.Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, -2)
end)
