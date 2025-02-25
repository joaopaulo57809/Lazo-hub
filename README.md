-- Script Avançado de Blox Fruits com Painel GUI Completo

-- Funções Utilitárias
local function createButton(parent, text, position, size, onClick)
    local button = Instance.new("TextButton")
    button.Parent = parent
    button.Text = text
    button.Position = position
    button.Size = size
    button.MouseButton1Click:Connect(onClick)
    button.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
    button.TextColor3 = Color3.fromRGB(255, 255, 255)
    return button
end

local function createToggleButton(parent, text, position, size, onToggle)
    local button = createButton(parent, text, position, size, function()
        local toggled = not button.Toggled
        button.Toggled = toggled
        onToggle(toggled)
        button.Text = toggled and "Desativar " .. text or "Ativar " .. text
    end)
    button.Toggled = false
    return button
end

-- Painel Principal
local screenGui = Instance.new("ScreenGui")
local mainFrame = Instance.new("Frame")

screenGui.Name = "BloxFruitsAdvancedPanel"
screenGui.Parent = game.CoreGui
mainFrame.Parent = screenGui

mainFrame.Position = UDim2.new(0.5, -250, 0.5, -200)
mainFrame.Size = UDim2.new(0, 500, 0, 400)
mainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)

-- Título do Painel
local titleLabel = Instance.new("TextLabel")
titleLabel.Parent = mainFrame
titleLabel.Text = "Painel Avançado Blox Fruits"
titleLabel.Position = UDim2.new(0.5, -125, 0, 10)
titleLabel.Size = UDim2.new(0, 250, 0, 50)
titleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
titleLabel.BackgroundTransparency = 1

-- Botão Fechar/Abrir
local toggleButton = createButton(mainFrame, "Fechar", UDim2.new(0, 10, 0, 10), UDim2.new(0, 100, 0, 50), function()
    mainFrame.Visible = not mainFrame.Visible
    toggleButton.Text = mainFrame.Visible and "Fechar" or "Abrir"
end)

-- Sessão de Funções
local sectionFrame = Instance.new("Frame")
sectionFrame.Parent = mainFrame
sectionFrame.Position = UDim2.new(0, 10, 0, 70)
sectionFrame.Size = UDim2.new(1, -20, 1, -80)
sectionFrame.BackgroundTransparency = 1

-- Exemplo de Funções Avançadas (sem aimbot ou auto bounty)
createToggleButton(sectionFrame, "Farm Automático", UDim2.new(0, 0, 0, 0), UDim2.new(0, 200, 0, 50), function(toggled)
    -- Função de farm automático aqui
end)

createToggleButton(sectionFrame, "Teleporte Seguro", UDim2.new(0, 0, 0, 60), UDim2.new(0, 200, 0, 50), function(toggled)
    -- Função de teleporte seguro aqui
end)

createToggleButton(sectionFrame, "Aumento de XP", UDim2.new(0, 0, 0, 120), UDim2.new(0, 200, 0, 50), function(toggled)
    -- Função de aumento de XP aqui
end)

createToggleButton(sectionFrame, "Auto Skill", UDim2.new(0, 0, 0, 180), UDim2.new(0, 200, 0, 50), function(toggled)
    -- Função de auto skill aqui
end)

createToggleButton(sectionFrame, "Auto Quest", UDim2.new(0, 0, 0, 240), UDim2.new(0, 200, 0, 50), function(toggled)
    -- Função de auto quest aqui
end)

-- Outras funcionalidades úteis e seguras
createToggleButton(sectionFrame, "Detector de Frutas
