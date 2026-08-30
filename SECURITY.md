# FritzScope security and antivirus transparency

## Supported version

Security corrections are provided only for the latest public beta. The currently supported release is **FritzScope v3.1.7B for Windows x64**. Earlier beta binaries remain available for historical reference but are not guaranteed to receive fixes.

## Report a vulnerability privately

Use the repository's **Security → Report a vulnerability** form. Do not publish credentials, FRITZ!Box Support Data, public or local IP addresses, MAC addresses, device names, telephone numbers or private logs in an Issue or Discussion.

Useful information includes the FritzScope version, Windows version, minimal reproduction steps and the SHA-256 of the downloaded file. Do not attach a real `Dados` folder. Reports about FRITZ!OS itself or FRITZ!Box hardware must be sent to FRITZ! GmbH; this is an independent project and cannot correct router firmware.

There is currently no bug-bounty programme. Responsible, coordinated reporting is appreciated.

## v3.1.7B executable verification

The exact public executable has these properties:

- File: `FritzScope-v3.1.7B-Windows.exe`
- Size: `949,760 bytes`
- SHA-256: `37B950837681E72D9D45968C72DEAACCB2F190D8DAC2DF8B895FF7DA50190B14`
- File and assembly version: `3.1.7.0`
- Architecture: managed .NET Framework 4.8, PE32+ AMD64
- Manifest: `asInvoker`, `uiAccess=false`
- Authenticode: not yet digitally signed

The file was analysed by [VirusTotal](https://www.virustotal.com/gui/file/37b950837681e72d9d45968c72deaaccb2f190d8dac2df8b895ff7da50190b14/detection) on 30 August 2026. At the recorded analysis state, **3 of 71 engines** returned generic detections:

- McAfee Scanner — `Ti!37B950837681`
- SecureAge — `Malicious`
- VirIT — `Trojan.Win64.MSIL_Heur.A`

Elastic, Malwarebytes and MaxSecure, which flagged v3.1.6B, reported v3.1.7B as `Undetected`. Microsoft, Bitdefender, Kaspersky, ESET, Avast/AVG, Sophos, Fortinet, SentinelOne and the other major engines also reported `Undetected` in that analysis.

A generic detection can be a false positive, particularly for a new and unsigned low-prevalence executable, but a VirusTotal score is not proof that software is safe or malicious. Results can change when vendors update their engines. Do not disable antivirus protection; confirm the filename, source and SHA-256 and review the current analysis.

Immediately before publication, Microsoft Defender was active with real-time protection and signature version `1.457.409.0`. Custom scans of the final EXE and ZIP produced **zero new detections**.

## What was audited and changed

The previous v3.1.6B executable was inspected because several sandbox labels alleged WMI, debugger detection, process injection, LSASS access and obfuscation. The application source and compiled PE contained none of those functions:

- no `System.Management` or WMI reference;
- no debugger-detection API;
- no process-injection, remote-memory or LSASS API;
- no PowerShell, `cmd.exe`, script host, service or scheduled-task execution;
- no packer, obfuscator or payload appended after the PE sections;
- the only native import is the normal .NET entry point `mscoree.dll!_CorExeMain`.

v3.1.7B nevertheless removes avoidable heuristic triggers and improves consent:

- the history folder is opened through the Windows shell without directly executing `explorer.exe`;
- the manual single-port TCP test uses `ConnectAsync` with a bounded asynchronous timeout instead of a blocking wait handle;
- an unknown OUI requires a separate confirmation before `api.maclookup.app` receives only the first three MAC bytes;
- the executable is built explicitly for x64 with a non-elevated manifest, high-entropy ASLR and code-integrity compiler flags.

The application still performs legitimate network-diagnostic work. It sends a short ICMP test to `1.1.1.1`, communicates locally with the configured FRITZ!Box and writes its own local history under `%LocalAppData%\FritzScope`. IP-location, unknown-OUI lookup, a manual TCP endpoint test and the PayPal page require explicit user action.

---

# Segurança e transparência antimalware do FritzScope

## Versão suportada

As correções de segurança são fornecidas apenas para a beta pública mais recente. A versão atualmente suportada é o **FritzScope v3.1.7B para Windows x64**. Os binários anteriores permanecem disponíveis como referência histórica, mas não têm correções garantidas.

## Comunicar uma vulnerabilidade em privado

Usa o formulário **Security → Report a vulnerability** do repositório. Não publiques credenciais, Support Data da FRITZ!Box, IPs públicos ou locais, MACs, nomes de aparelhos, números de telefone ou registos privados numa Issue ou Discussion.

Indica a versão do FritzScope, a versão do Windows, passos mínimos para reproduzir e o SHA-256 do ficheiro transferido. Não anexes uma pasta `Dados` real. Problemas do próprio FRITZ!OS ou do hardware FRITZ!Box devem ser enviados à FRITZ! GmbH; este projeto é independente e não pode corrigir firmware do router.

Não existe atualmente um programa de recompensas. A comunicação responsável e coordenada é bem-vinda.

## Verificação do executável v3.1.7B

O executável público exato possui estas propriedades:

- Ficheiro: `FritzScope-v3.1.7B-Windows.exe`
- Tamanho: `949.760 bytes`
- SHA-256: `37B950837681E72D9D45968C72DEAACCB2F190D8DAC2DF8B895FF7DA50190B14`
- Versão do ficheiro e assembly: `3.1.7.0`
- Arquitetura: .NET Framework 4.8 gerido, PE32+ AMD64
- Manifesto: `asInvoker`, `uiAccess=false`
- Authenticode: ainda sem assinatura digital

O ficheiro foi analisado pelo [VirusTotal](https://www.virustotal.com/gui/file/37b950837681e72d9d45968c72deaaccb2f190d8dac2df8b895ff7da50190b14/detection) em 30 de agosto de 2026. No estado registado da análise, **3 de 71 motores** apresentaram deteções genéricas:

- McAfee Scanner — `Ti!37B950837681`
- SecureAge — `Malicious`
- VirIT — `Trojan.Win64.MSIL_Heur.A`

Elastic, Malwarebytes e MaxSecure, que tinham assinalado a v3.1.6B, indicaram `Undetected` na v3.1.7B. Microsoft, Bitdefender, Kaspersky, ESET, Avast/AVG, Sophos, Fortinet, SentinelOne e os restantes motores principais também indicaram `Undetected` nessa análise.

Uma deteção genérica pode ser um falso positivo, sobretudo num executável novo, pouco prevalente e ainda sem assinatura, mas a pontuação do VirusTotal não prova que um programa é seguro ou malicioso. Os resultados podem mudar quando os fornecedores atualizam os motores. Não desatives o antivírus; confirma o nome, a origem, o SHA-256 e a análise atual.

Imediatamente antes da publicação, o Microsoft Defender estava ativo, com proteção em tempo real e assinaturas `1.457.409.0`. As verificações personalizadas do EXE e do ZIP finais produziram **zero novas deteções**.

## O que foi auditado e alterado

O executável v3.1.6B foi inspecionado porque alguns rótulos de sandbox alegavam WMI, deteção de debugger, injeção de processos, acesso ao LSASS e ofuscação. Nem o código da aplicação nem o PE compilado contêm essas funções:

- sem referência a `System.Management` ou WMI;
- sem API de deteção de debugger;
- sem APIs de injeção, memória remota ou LSASS;
- sem execução de PowerShell, `cmd.exe`, script host, serviço ou tarefa agendada;
- sem packer, ofuscador ou payload anexado depois das secções PE;
- a única importação nativa é a entrada normal do .NET `mscoree.dll!_CorExeMain`.

A v3.1.7B remove ainda sinais heurísticos evitáveis e melhora o consentimento:

- a pasta do histórico é aberta através da shell do Windows sem executar diretamente `explorer.exe`;
- o teste manual de uma única porta usa `ConnectAsync` com limite assíncrono em vez de um wait handle bloqueante;
- um OUI desconhecido exige confirmação separada antes de `api.maclookup.app` receber apenas os primeiros três bytes do MAC;
- o executável é compilado explicitamente para x64 com manifesto sem elevação, ASLR de entropia elevada e flags de integridade de código.

A aplicação continua a executar diagnóstico legítimo da rede. Envia um pequeno teste ICMP para `1.1.1.1`, comunica localmente com a FRITZ!Box configurada e grava o seu próprio histórico em `%LocalAppData%\FritzScope`. Localização de IP, consulta de OUI desconhecido, teste TCP manual e abertura do PayPal exigem uma ação explícita do utilizador.
