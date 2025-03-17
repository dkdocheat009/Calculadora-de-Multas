RegisterCommand("calculamulta", function(source, args)
    local tipoMulta = args[1]
    local valorBase = 0

    if tipoMulta == "velocidade" then
        valorBase = 500
    elseif tipoMulta == "acidente" then
        valorBase = 1000
    elseif tipoMulta == "estacionamento" then
        valorBase = 300
    else
        TriggerClientEvent('chat:addMessage', source, { args = { "Erro", "Tipo de multa inválido!" } })
        return
    end

    TriggerClientEvent('chat:addMessage', source, { args = { "Calculadora", "A multa para " .. tipoMulta .. " é de R$" .. valorBase } })
end)
