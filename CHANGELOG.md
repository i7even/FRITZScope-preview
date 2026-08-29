# FritzScope changelog · Registo de alterações

This file records functional changes in the published binary. It never contains router logs, public or local IP addresses, MAC addresses, device names, credentials or other data from a real installation.

Este ficheiro regista alterações funcionais do binário publicado. Nunca contém registos do router, endereços IP públicos ou locais, endereços MAC, nomes de aparelhos, credenciais nem outros dados de uma instalação real.

## v3.1.6B — Public-IP history and diagnostic timeline · Histórico do IP público e linha temporal de diagnóstico

### English

- Adds a **Recent public IP log** card to Overview, with the number of observed assignments and changes plus the latest transitions.
- Shows the previous and new public IP address, date and time, and evidence source when that information is available.
- Adds direct actions to open Events, open the complete recent-IP list, and show or hide addresses.
- Applies address masking consistently to Overview, Events and the recent-IP list.
- Builds the diagnostic timeline from the dedicated local public-IP history and removes duplicate generic events from the visible list.
- Keeps complete public IP addresses only in the dedicated local history; they are not duplicated into the general timeline CSV.
- Adds a public-IP change summary to History.
- Corrects partial-reading logic so an unavailable general event source is not presented as a confirmed zero WAN-failure result when IP history is still available.
- Improves responsive card sizing after toggling address visibility.
- Updates PT-PT and EN Global labels and source explanations.
- Makes priority deviations interactive and explains the reason, measured evidence and destination for each verification.
- Highlights devices that still need identification in yellow and allows an existing identity to be reviewed or removed.
- Uses the included local OUI database first, prevents private or random MAC addresses from being sent externally, and removes the obsolete browser-search path.
- Improves the presentation of advanced FRITZ!Box services and removes unused ASUS-router and Telegram configuration controls.

### Português

- Adiciona à Vista Geral o cartão **Registo recente de IP público**, com o número de atribuições e mudanças observadas e as transições mais recentes.
- Mostra o IP público anterior e o novo, data e hora e origem da evidência quando essas informações estão disponíveis.
- Adiciona ações diretas para abrir Eventos, abrir a lista completa de IPs recentes e mostrar ou ocultar endereços.
- Aplica a ocultação de endereços de forma consistente na Vista Geral, nos Eventos e na lista de IPs recentes.
- Constrói a linha temporal de diagnóstico a partir do histórico local dedicado do IP público e remove da lista visível os eventos genéricos duplicados.
- Mantém os IPs públicos completos apenas no histórico local dedicado; não os duplica no CSV geral da linha temporal.
- Adiciona ao Histórico um resumo das mudanças do IP público.
- Corrige o tratamento de leituras parciais para não apresentar falsamente zero falhas WAN quando a fonte geral de eventos está indisponível, mas o histórico do IP continua acessível.
- Melhora o dimensionamento responsivo dos cartões depois de mostrar ou ocultar endereços.
- Atualiza textos e explicações de origem em PT-PT e EN Global.
- Torna os desvios prioritários interativos e explica o motivo, a evidência medida e o destino de cada verificação.
- Realça a amarelo os aparelhos que ainda precisam de identificação e permite rever ou remover uma identidade existente.
- Usa primeiro a base OUI local incluída, impede o envio externo de MACs privados ou aleatórios e remove o antigo caminho de pesquisa no navegador.
- Melhora a apresentação dos serviços avançados da FRITZ!Box e remove os controlos sem utilização de configuração de router ASUS e Telegram.

## Download integrity · Integridade das transferências

The exact file sizes and SHA-256 checksums for the current release are published in [`DOWNLOAD.md`](DOWNLOAD.md) and in the GitHub release notes.

Os tamanhos exatos e os SHA-256 da versão atual são publicados em [`DOWNLOAD.md`](DOWNLOAD.md) e nas notas da versão do GitHub.
