# Painel de NFS-e — demonstração (Cruz Sociedade de Contadores)

Modelo navegável do painel de gestão e uso do sistema de emissão automática de NFS-e.

**Todos os dados são simulados**: nomes, CNPJs, e-mails, notas, chaves, logs, configurações e área de administração. Nada é enviado a servidores, ao Emissor Nacional, ao OneDrive, a e-mails ou ao Claude.

Acesso de teste (qualquer senha com 8+ caracteres): `administrador@cruz.example` (Administrador), `gerente@cruz.example` (Gerente), `aprovador1@cruz.example` (Aprovador), `visualizador1@cruz.example` (bloqueada, para testar o aviso) e `visualizador2@cruz.example` (bloqueado). O código do MFA aparece na própria tela de login.

## Níveis (v11)

Seletor de nível no topo de todas as telas (Padrão e Profissional, definidos por licença; o Essencial foi removido) e a tela **Níveis e recursos** (comparação, fases e itens fora dos níveis). Por padrão a demonstração não mostra valores nem horas: para exibi-los, altere `MOSTRAR_VALORES` para `true` no final do `index.html`.

## Licenciamento (v12)

Aviso permanente no topo de todas as telas conforme o estado da licença (avisos aos 60, 30 e 15 dias, tolerância de 15 dias após o vencimento e aviso de licença vencida). **Licença vencida nunca bloqueia a emissão de notas nem o acesso aos dados**: depois da tolerância, ficam bloqueados apenas novos usuários, alterações de configuração e atualizações. O aviso não aparece em notas, PDFs, XMLs nem em e-mails aos clientes.

Em **Licenciamento** há o resumo de suporte e banco de horas (mês da entrega com manuais e dúvidas de uso; depois, suporte pago e adaptações orçadas à parte) e um simulador dos cinco estados da licença, só para a demonstração. Valores de licença só aparecem com `MOSTRAR_VALORES=true`.

## Novidades da versão 14 (branch `v14-padrao-profissional`)

- Dois níveis, definidos por licença: **Padrão** e **Profissional**. Licença por usuário, mensal ou anual (valores a definir).
- **Relatórios:** até 3 no Padrão; todos no Profissional (8 por cliente e 5 do administrador: API do Claude, fluxo de e-mails, acessos, backups e motor fiscal).
- **Autonomia por regra:** tela com a "cápsula de acerto" por cliente e precisão mínima definida pelo administrador. O cancelamento é sempre manual.
- **Número da NFS-e** na lista de pedidos; **IBS/CBS** (alíquotas de teste, exemplo) no detalhe da nota.
- **Backup** só na VPS, com os riscos descritos na tela Backups. O backup em nuvem é um serviço opcional, sob consulta.
- **Sem treinamento:** manuais de uso em PDF e esclarecimento de dúvidas de uso nos 30 dias após a entrega (tela Ajuda e suporte).
- Usuários de teste com nomes genéricos por perfil: `gerente@`, `administrador@`, `aprovador1@`, `aprovador2@`, `visualizador1@` e `visualizador2@` (`@cruz.example`).
- **Mensagens automáticas** (e-mail aos clientes e WhatsApp aos usuários): fixas no Padrão; o administrador personaliza no Profissional (Configurações, aba Mensagens).
- **Bot de triagem e atendimento:** serviço opcional, sob consulta.
- **Licença vencida:** tolerância de 15 dias; de 16 a 30 dias, modo restrito (autonomia desligada, relatórios, módulos do Profissional, novos usuários e configurações suspensos); acima de 30 dias, modo básico. A emissão, o cancelamento e o acesso aos dados nunca são bloqueados. Use o simulador em Licenciamento.

## Ajustes da versão 14 (diferença entre Padrão e Profissional)
- **Autonomia em dois degraus.** Padrão: mínimo geral de acerto, com regra única para todos os clientes. Profissional: por cliente e tipo de serviço, com modo manual, semiautomático (janela de veto) ou automático, e limite de valor por nota. O botão "Pausar automático" existe nos dois. O cancelamento é sempre manual.
- **Validade das procurações (Profissional).** Tela com o vencimento de cada cliente, avisos configuráveis (por exemplo, 60, 30 e 15 dias) e registro dos avisos enviados.
- **Exportação mensal (Profissional).** Planilha CSV das notas do mês e resumo por cliente, com envio automático por e-mail em um dia fixo. Alíquotas de exemplo.
- **Nos dois níveis:** pasta de cada cliente no padrão da Cruz e cancelamento com autorização.
- No Padrão, as telas do Profissional aparecem com a descrição do que ficam disponíveis ao contratar o nível.
