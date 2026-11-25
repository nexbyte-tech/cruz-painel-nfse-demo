# Painel de NFS-e — demonstração (Cruz Sociedade de Contadores)

Modelo navegável do painel de gestão e uso do sistema de emissão automática de NFS-e.

**Todos os dados são simulados**: nomes, CNPJs, e-mails, notas, chaves, logs, configurações e área de administração. Nada é enviado a servidores, ao Emissor Nacional, ao OneDrive, a e-mails ou ao Claude.

Acesso de teste (qualquer senha com 8+ caracteres): `administrador@cruz.example` (Administrador), `gerente@cruz.example` (Gerente), `aprovador1@cruz.example` (Aprovador), `visualizador1@cruz.example` (bloqueada, para testar o aviso) e `visualizador2@cruz.example` (bloqueado). O código do MFA aparece na própria tela de login.

## Níveis (v11)

Seletor de nível no topo de todas as telas (Padrão e Profissional, definidos por licença; o Essencial foi removido) e a tela **Níveis e recursos** (comparação, fases e itens fora dos níveis). Por padrão a demonstração não mostra valores nem horas: para exibi-los, altere `MOSTRAR_VALORES` para `true` no final do `index.html`.

## Licenciamento (v12)

Aviso permanente no topo de todas as telas conforme o estado da licença (avisos aos 60, 30 e 15 dias, tolerância de 15 dias após o vencimento e aviso de licença vencida). **Licença vencida nunca bloqueia a emissão de notas nem o acesso aos dados**: depois da tolerância, ficam bloqueados apenas novos usuários, alterações de configuração e atualizações. O aviso não aparece em notas, PDFs, XMLs nem em e-mails aos clientes.

Em **Licenciamento** há o resumo de suporte e banco de horas (6 h no mês 1, 2 h por mês nos meses 2 e 3, banco de 4 h por ano a partir do mês 4) e um simulador dos cinco estados da licença, só para a demonstração. Valores de licença só aparecem com `MOSTRAR_VALORES=true`.
