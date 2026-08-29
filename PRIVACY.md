# FritzScope privacy notice

This notice describes the public Windows beta `v3.1.3B`. FritzScope is a local desktop application. It has no project account, advertising, analytics, cloud dashboard or automatic telemetry.

## Data stored on the computer

- Connection data, measurements and local events are stored under `%LocalAppData%\FritzScope\Dados` on a new installation. Interface preferences are stored under `%LocalAppData%\FritzScope\Config`.
- A saved FRITZ!Box credential is protected for the current Windows user with Windows DPAPI.
- Device activity can contain a device name, local IP address and MAC address for up to 30 days.
- Numeric Scope history is kept for up to 31 days, with a defensive 32 MiB limit, and contains no device names, IP addresses, MAC addresses, SSIDs or credentials.
- Manufacturer/OUI results selected by the user can be cached locally.

## Network communication

- Normal readings are exchanged directly between the Windows computer and the FRITZ!Box on the local network. TR-064 may use local unencrypted HTTP.
- The ICMP test targets `1.1.1.1`; it is a small local connectivity test, not a formal ISP SLA measurement.
- No IP-location or MAC-vendor request runs automatically.
- A user-confirmed IP lookup sends only the selected public IP to `api.ipapi.is`; `ipwho.is` can be used as a fallback.
- **Identify** sends only the first three bytes of a MAC address (the OUI) to the maclookup service after the user invokes it.
- **Search online** opens the default browser with an OUI-based Google search only after the user chooses that action.
- The PayPal donation page opens only after the user selects the optional donation button.

Each external provider processes a manually submitted request under its own terms and privacy policy. FritzScope does not operate those services and does not receive the provider's logs.

## Deleting local data and uninstalling

1. Exit FritzScope from its notification-area icon.
2. Delete the portable FritzScope application folder.
3. Delete `%LocalAppData%\FritzScope` to remove current local history, interface preferences and protected credentials.
4. If a legacy portable copy used a local `Dados` folder beside the executable, delete that folder too.

FritzScope has no project cloud account to delete. Do not upload or redistribute a local `Dados` folder because it may contain private network information.

---

# Aviso de privacidade do FritzScope

Este aviso descreve a beta pública `v3.1.3B` para Windows. O FritzScope é uma aplicação local: não possui conta do projeto, publicidade, analytics, painel cloud nem telemetria automática.

## Dados guardados no computador

- Numa instalação nova, os dados da ligação, as medições e os eventos locais são guardados em `%LocalAppData%\FritzScope\Dados`. As preferências da interface são guardadas em `%LocalAppData%\FritzScope\Config`.
- Uma credencial da FRITZ!Box guardada é protegida pelo Windows DPAPI para o utilizador atual do Windows.
- A atividade dos aparelhos pode conter nome, IP local e MAC durante um máximo de 30 dias.
- O histórico numérico do Scope é conservado até 31 dias, com limite defensivo de 32 MiB, e não contém nomes, IPs, MACs, SSIDs nem credenciais.
- Resultados de fabricante/OUI pedidos pelo utilizador podem ser guardados numa cache local.

## Comunicações de rede

- As leituras normais são trocadas diretamente entre o computador e a FRITZ!Box na rede local. O TR-064 pode usar HTTP local sem encriptação.
- O teste ICMP usa `1.1.1.1`; é um pequeno teste local de conectividade e não uma medição formal do SLA do operador.
- Nenhuma consulta de localização de IP ou fabricante MAC é feita automaticamente.
- Uma consulta de IP confirmada pelo utilizador envia apenas o IP público escolhido para `api.ipapi.is`; `ipwho.is` pode ser usado como alternativa.
- **Identificar** envia apenas os primeiros três bytes do MAC (OUI) para o serviço maclookup depois de o utilizador escolher essa ação.
- **Pesquisar online** abre o navegador predefinido com uma pesquisa Google baseada no OUI apenas depois de o utilizador pedir essa ação.
- A página PayPal só abre quando é escolhido o botão de donativo opcional.

Cada fornecedor externo trata o pedido manual segundo os seus próprios termos e política de privacidade. O FritzScope não opera esses serviços nem recebe os respetivos registos.

## Apagar os dados locais e desinstalar

1. Sai completamente do FritzScope através do ícone junto ao relógio.
2. Apaga a pasta portátil da aplicação FritzScope.
3. Apaga `%LocalAppData%\FritzScope` para remover histórico, preferências da interface e credenciais protegidas atuais.
4. Se uma versão portátil antiga utilizou uma pasta `Dados` ao lado do executável, apaga também essa pasta.

O FritzScope não tem uma conta cloud do projeto para eliminar. Nunca carregues nem redistribuas a pasta local `Dados`, porque poderá conter informações privadas da rede.
