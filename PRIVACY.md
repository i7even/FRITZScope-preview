# FritzScope privacy notice

This notice describes the public Windows x64 beta `v3.1.7B`. FritzScope is a local desktop application. It has no project account, advertising, analytics, cloud dashboard or automatic telemetry.

## Data stored on the computer

- Connection data, measurements and local events are stored under `%LocalAppData%\FritzScope\Dados` on a new installation. Interface preferences are stored under `%LocalAppData%\FritzScope\Config`.
- A saved FRITZ!Box credential is protected for the current Windows user with Windows DPAPI.
- Device activity can contain a device name, local IP address and MAC address for up to 30 days.
- Numeric Scope history is kept for up to 31 days, with a defensive 32 MiB limit, and contains no device names, IP addresses, MAC addresses, SSIDs or credentials.
- Public-IP history stores the complete IPv4 address, timestamp and source locally for up to 365 days and at most 400 observed assignments. The general event timeline does not duplicate those complete addresses into its CSV file.
- Confirmed device identities are associated locally with a deterministic SHA-256 hash of the complete normalised MAC address. The identity file does not store the MAC address, IP address or device name in plain text; the hash is a pseudonymous identifier, not anonymisation. A user can remove it with **Undo identification** or by deleting the local data. The defensive limits are 4,096 identities and 4 MiB.
- Manufacturer/OUI results selected by the user can be cached locally. A private or random MAC address is not sent to the vendor service or to a browser search.

## Network communication

- Normal readings are exchanged directly between the Windows computer and the FRITZ!Box on the local network. TR-064 may use local unencrypted HTTP.
- The ICMP test targets `1.1.1.1`; it is a small local connectivity test, not a formal ISP SLA measurement.
- No IP-location or MAC-vendor request runs automatically.
- A user-confirmed IP lookup sends only the selected public IP to `api.ipapi.is`; `ipwho.is` can be used as a fallback.
- **Identify** checks the built-in database and local cache first. When the OUI remains unknown, it shows a separate confirmation naming `api.maclookup.app` and the exact OUI. Only after approval does it send those first three bytes; the complete MAC address, IP address and device name are not sent.
- The PayPal donation page opens only after the user selects the optional donation button.

Each external provider processes a manually submitted request under its own terms and privacy policy. FritzScope does not operate those services and does not receive the provider's logs.

## Deleting local data and uninstalling

1. Exit FritzScope from its notification-area icon.
2. Delete the portable FritzScope application folder.
3. Delete `%LocalAppData%\FritzScope` to remove current local history, interface preferences and protected credentials.
4. If a `Dados` folder exists beside the executable, delete that folder too. This also removes any `.bak` copies stored inside those data folders.

FritzScope has no project cloud account to delete. Do not upload or redistribute a local `Dados` folder because it may contain private network information.

---

# Aviso de privacidade do FritzScope

Este aviso descreve a beta pública `v3.1.7B` para Windows x64. O FritzScope é uma aplicação local: não possui conta do projeto, publicidade, analytics, painel cloud nem telemetria automática.

## Dados guardados no computador

- Numa instalação nova, os dados da ligação, as medições e os eventos locais são guardados em `%LocalAppData%\FritzScope\Dados`. As preferências da interface são guardadas em `%LocalAppData%\FritzScope\Config`.
- Uma credencial da FRITZ!Box guardada é protegida pelo Windows DPAPI para o utilizador atual do Windows.
- A atividade dos aparelhos pode conter nome, IP local e MAC durante um máximo de 30 dias.
- O histórico numérico do Scope é conservado até 31 dias, com limite defensivo de 32 MiB, e não contém nomes, IPs, MACs, SSIDs nem credenciais.
- O histórico do IP público guarda localmente o IPv4 completo, data/hora e origem durante um máximo de 365 dias e 400 atribuições observadas. A linha temporal geral não duplica esses endereços completos no respetivo ficheiro CSV.
- As identidades confirmadas dos aparelhos são associadas localmente a um hash SHA-256 determinístico do MAC completo normalizado. O ficheiro de identidades não guarda o MAC, o IP nem o nome do aparelho em texto simples; o hash é um identificador pseudónimo, não uma anonimização. O utilizador pode removê-lo através de **Desfazer identificação** ou apagando os dados locais. Os limites defensivos são 4.096 identidades e 4 MiB.
- Resultados de fabricante/OUI pedidos pelo utilizador podem ser guardados numa cache local. Um MAC privado ou aleatório não é enviado ao serviço de fabricante nem para uma pesquisa no navegador.

## Comunicações de rede

- As leituras normais são trocadas diretamente entre o computador e a FRITZ!Box na rede local. O TR-064 pode usar HTTP local sem encriptação.
- O teste ICMP usa `1.1.1.1`; é um pequeno teste local de conectividade e não uma medição formal do SLA do operador.
- Nenhuma consulta de localização de IP ou fabricante MAC é feita automaticamente.
- Uma consulta de IP confirmada pelo utilizador envia apenas o IP público escolhido para `api.ipapi.is`; `ipwho.is` pode ser usado como alternativa.
- **Identificar** consulta primeiro a base incluída e a cache local. Quando o OUI continua desconhecido, apresenta uma confirmação separada que identifica `api.maclookup.app` e o OUI exato. Só depois da autorização envia esses primeiros três bytes; o MAC completo, IP e nome do aparelho não são enviados.
- A página PayPal só abre quando é escolhido o botão de donativo opcional.

Cada fornecedor externo trata o pedido manual segundo os seus próprios termos e política de privacidade. O FritzScope não opera esses serviços nem recebe os respetivos registos.

## Apagar os dados locais e desinstalar

1. Sai completamente do FritzScope através do ícone junto ao relógio.
2. Apaga a pasta portátil da aplicação FritzScope.
3. Apaga `%LocalAppData%\FritzScope` para remover histórico, preferências da interface e credenciais protegidas atuais.
4. Se existir uma pasta `Dados` ao lado do executável, apaga também essa pasta. Isto remove igualmente as cópias `.bak` guardadas dentro dessas pastas de dados.

O FritzScope não tem uma conta cloud do projeto para eliminar. Nunca carregues nem redistribuas a pasta local `Dados`, porque poderá conter informações privadas da rede.
