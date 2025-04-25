-- Criar GUI
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local ZombieLegsButton = Instance.new("zombie leg🧟")
local IceLegsButton = Instance.new("ice leg❄️")

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.Name = "LegSwapHub"

Frame.Size = UDim2.new(0, 200, 0, 150)
Frame.Position = UDim2.new(0.1, 0, 0.2, 0)
Frame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
Frame.Parent = ScreenGui

ZombieLegsButton.Size = UDim2.new(1, -20, 0, 50)
ZombieLegsButton.Position = UDim2.new(0, 10, 0, 10)
ZombieLegsButton.Text = "Pernas de Zumbi"
ZombieLegsButton.BackgroundColor3 = Color3.fromRGB(80, 80, 80)
ZombieLegsButton.TextColor3 = Color3.new(1, 1, 1)
ZombieLegsButton.Parent = Frame

IceLegsButton.Size = UDim2.new(1, -20, 0, 50)
IceLegsButton.Position = UDim2.new(0, 10, 0, 70)
IceLegsButton.Text = "Perna de Gelo"
IceLegsButton.BackgroundColor3 = Color3.fromRGB(80, 80, 80)
IceLegsButton.TextColor3 = Color3.new(1, 1, 1)
IceLegsButton.Parent = Frame

-- IDs das pernas
local zombieLeftLegID = 834679655
local zombieRightLegID = 834679884

local iceLeftLegID = 139572789
local iceRightLegID = 139572789

-- Função para trocar pernas
local function trocarPernas(leftID, rightID)
    local humanoid = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
    if humanoid then
        local desc = humanoid:GetAppliedDescription()
        desc.LeftLeg = leftID
        desc.RightLeg = rightID
        humanoid:ApplyDescription(desc)
    end
end

-- Botões
ZombieLegsButton.MouseButton1Click:Connect(function()
    trocarPernas(zombieLeftLegID, zombieRightLegID)
end)

IceLegsButton.MouseButton1Click:Connect(function()
    trocarPernas(iceLeftLegID, iceRightLegID)
end)
