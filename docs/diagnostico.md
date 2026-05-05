# Diagnóstico e Redesenho do Processo de Transporte
## Schulz S.A.

**Cliente:** Schulz S.A.
**Unidade:** Joinville, Santa Catarina
**Período de elaboração:** Março e abril de 2026
**Elaboração:** Consolida em parceria com Lincros
**Áreas envolvidas:** Logística, Compras, Recebimento Fiscal, Financeiro, Controladoria, TIC, RVA, Vendas e Revenda
**Versão:** 1.0

---

## Sumário Executivo

Este documento apresenta o resultado do trabalho de diagnóstico e redesenho do processo de transporte da Schulz, conduzido em duas etapas. A primeira foi a reunião de mapeamento realizada na unidade de Joinville em 18 de março de 2026, com a participação dos gestores e representantes das áreas envolvidas. A segunda foi o detalhamento técnico do redesenho, que traduz as dores levantadas em fluxos operacionais concretos no TMS Lincros, já implantado.

A escala do tema é relevante. A conta frete anual da Schulz, somando Automotiva e Compressores, é de cerca de 58 milhões de reais. A operação convive com sete portais distintos de transportadoras consultados manualmente várias vezes ao dia, dois perfis logísticos opostos (FOB na Automotiva e CIF nos Compressores), e cerca de 30% das entregas com agendamento feito unilateralmente pela transportadora.

O diagnóstico identificou sete dores prioritárias que, em conjunto, comprometem visibilidade, controle de custo e auditoria de frete. Seis dessas dores se resolvem por parametrização e treinamento dentro do Lincros. A sétima é de natureza diferente: é uma regra contratual que precisa ser incorporada ao processo de homologação de transportadoras conduzido por Compras. Sem ela, a torre operacional vai existir tecnicamente, mas vai operar parcialmente, porque parte da malha de transporte não vai alimentar o sistema.

O documento está organizado em nove capítulos. Os três primeiros descrevem contexto, escopo e a visão atual da operação. O quarto detalha as sete dores com seus respectivos redesenhos. Do quinto ao oitavo, são apresentados os elementos técnicos e contratuais que sustentam o projeto. O nono lista pendências e próximos passos.

---

## 1. Contexto Operacional

A Schulz S.A. opera duas frentes industriais com perfis logísticos opostos. A Automotiva atende montadoras com modelo majoritariamente FOB e operação milk run, em que o cliente coordena a coleta dentro de janelas pré-acordadas com o setor de GAC. Os pedidos chegam via EDI, o GAC monta a programação no TOTVS e comunica o transportador designado. Esse fluxo é estável e linear, e o esforço de gestão de frete é baixo porque a responsabilidade pós-expedição é do destinatário.

Os Compressores operam em regime CIF em 30 a 40% das entregas. A operação é mais complexa, com múltiplas origens de demanda, processo de cotação ativo, e uso de sistema para alçada de aprovação de spot. É nesse perfil que se concentram as dores estruturais mapeadas.

A unificação dos dois perfis em uma mesma plataforma de gestão é o objetivo do redesenho, e o TMS Lincros é a ferramenta escolhida. O trabalho parte do princípio de que a ferramenta está implantada e operacional, e foca no que precisa ser ajustado em termos de processo, parametrização e governança para que ela entregue valor pleno.

---

## 2. Escopo do Redesenho

O escopo inclui sete áreas, cada uma com um papel específico no processo redesenhado. A clareza do recorte é parte da entrega, porque evita o erro comum de tratar todas as áreas como donas de processo, o que costuma resultar em diluição de responsabilidade.

**RVA (Pós-venda e Garantias)** entra como dono de processo. É a área com o gap mais severo de visibilidade sobre coletas reversas, operação hoje conduzida exclusivamente por troca de e-mail com a transportadora.

**Vendas e Revenda** entra como dono de processo. Concentra o maior volume de dores estruturais, relacionadas a rastreamento, endereço de entrega, agendamento e operação do depósito terceirizado Censos.

**Compras** entra como filtro da base de transportadoras. A função no novo desenho é incorporar, ao processo de homologação, a obrigação contratual de que a transportadora publique ocorrências e status no Lincros. Esse ponto é desenvolvido no capítulo 6.

**Operação Censos**, embora seja parceiro externo, é incorporada ao redesenho como usuário do Lincros. Isso retira o caráter de operação opaca para a Schulz e devolve visibilidade sobre o que sai do depósito.

**TI e Projetos Lincros** entram como apoio técnico, com foco em integrações, parametrizações e habilitação dos usuários. Não são donos de processo de negócio.

**Manutenção** fica fora do escopo prioritário. As transferências entre unidades e os envios para fornecedores são coordenados diretamente, sem necessidade de torre de status. O único caso de visibilidade, o frete expresso emergencial para peças, é exceção e pode ser absorvido pela mesma estrutura sem desenho específico.

---

## 3. Visão Atual da Operação por Área (AS IS)

### 3.1 Logística e Expedição

A operação da Automotiva é majoritariamente FOB. Pedidos chegam via EDI, o GAC monta o agendamento no TOTVS, envia as notas fiscais para o transportador e determina o veículo. As transportadoras têm horários pré-definidos para coletas e tabelas de frete acordadas. A Irapuru, por exemplo, opera com seis janelas diárias programadas. A Sulista trabalha com agendamento por e-mail. A Expedição não solicita frete, apenas executa.

A operação dos Compressores tem perfil CIF em parte significativa do volume e é estruturalmente mais complexa. Há múltiplas origens de demanda (Planejamento de Produção, Planejamento de Materiais, Expedição, GAC), processo de cotação ativo, e uso de sistema para alçada de aprovação de spot. O Romaneio não é obrigatório para toda saída física, o que dificulta a rastreabilidade de ponta a ponta.

Quando há necessidade de carga expressa, seja por atraso de produção, atraso de matéria-prima ou pedido emergencial, o GAC ou Compras aciona transportadoras com tabela predefinida, comunicação por e-mail ou WhatsApp, e busca disponibilidade na ordem do menor preço. Esse fluxo não é sistêmico hoje, e isso impede o registro estruturado de quem aceita ou recusa frete ao longo do tempo.

### 3.2 Compras

Compras negocia tabelas de frete com as transportadoras, valida preço e prazo contratual, e acompanha coletas em fornecedores. Para cargas expressas, faz cotações pontuais. A aprovação de spot na Automotiva acontece por e-mail. Nos Compressores, há alçada definida em sistema. A divergência entre os dois perfis cria uma assimetria de controle interno difícil de auditar.

### 3.3 Recebimento Fiscal

O Recebimento Fiscal dá entrada no CT-e no sistema, entrega a via ao transportador como comprovante, e integra o XML para o TOTVS, que faz a interface com o Financeiro. Há prazo de 48 horas para lançar o documento, ou até o vencimento do frete, o que vier primeiro. O lançamento de frete de saída também passa por esse fluxo. Quando há divergência de modalidade (frete entra como CIF na nota e precisa ser trocado para FOB ou vice-versa), o lançamento exige correção manual e nem sempre há carta de correção, o que gera ponto de auditoria.

### 3.4 Financeiro

O Financeiro recebe os documentos para pagamento com prazo atual de 3 dias úteis antes do vencimento. A dor recorrente é o documento que não foi integrado a tempo no TOTVS. Quando isso acontece no mesmo dia do vencimento, o Financeiro paga sem janela para validar inconsistências, o que compromete o controle.

### 3.5 Controladoria

A Controladoria valida o peso do veículo contra a nota fiscal, confere se as evidências estão completas, e procura o responsável quando há divergência. As taxas extras (diárias, descargas, reentregas) são autorizadas hoje por e-mail, sem registro sistêmico. A pré-fatura funciona para fracionado, mas não está parametrizada para lotação, o que reduz a eficácia da conferência preventiva. As faturas chegam semanalmente e a Controladoria precisa repassar para o Financeiro com 3 dias úteis de antecedência.

### 3.6 RVA (Revenda Reversa)

A RVA é responsável pelos fretes de garantia, com emissão de nota fiscal pelo cliente. As transportadoras são previamente homologadas por Compras. Em casos emergenciais, a RVA solicita frete expresso ao Compras. A área hoje não tem visualização do tracking dessas entregas, o que a impede de responder ao cliente quando solicitada.

### 3.7 Vendas e Revenda

A operação tem alta similaridade com a dos Compressores. A área precisa de visibilidade sobre onde está a mercadoria, e hoje consulta cada transportador no respectivo portal manualmente. O estoque opera dentro de um terceiro, o Censos, que recebe o XML da nota fiscal, etiqueta os volumes no padrão Schulz e separa para coleta. Hoje a baixa do romaneio é manual, feita em deslocamento físico, e a solicitação de cargas dedicadas segue caminho à parte. A transportadora faz agendamento direto com o cliente em cerca de 30% das entregas, sem participação da Schulz, o que retira o controle do prazo prometido.

---

## 4. Sete Dores Prioritárias

A partir do mapeamento das áreas, foram identificadas sete dores prioritárias. Cada uma é apresentada com a situação atual, o redesenho proposto e, quando aplicável, as pendências de validação técnica.

### 4.1 Rastreamento de Cargas

**Situação atual.** A equipe de Vendas consulta sete portais de transportadoras diferentes cerca de dez vezes por dia para responder representantes e clientes. A RVA acompanha coletas reversas por troca de e-mail, sem status fidedigno de etapa nem de localização. O cliente final pressiona a área interna porque não recebe visibilidade direta.

**Redesenho.** A Schulz passa a operar uma torre única no Lincros, consolidando o status de todas as transportadoras em uma só interface. O recebimento de status acontece pelo padrão EDI Proceda, que já está preparado para diferentes tipos de ocorrência. Para cada transportadora homologada, configura-se um de/para entre a nomenclatura dela e o padrão Schulz, o que elimina a divergência semântica entre transportadoras. Quando a transportadora não tem capacidade de envio automático, ela faz o input manual no portal. O cliente final passa a receber notificação automática de status pelo próprio Lincros. A área interna deixa de ser ponto de consulta para virar ponto de exceção.

### 4.2 Endereço de Entrega Divergente do Fiscal

**Situação atual.** O cliente fatura na matriz e recebe em CDA ou depósito. A equipe altera manualmente a nota ou comunica o endereço de entrega por e-mail à transportadora, com risco de erro e sem rastreabilidade.

**Redesenho.** O Lincros tem campo dedicado para endereço de entrega independente do destinatário fiscal, alimentado pela integração. O endereço viaja junto com a Ordem de Coleta, sem passar por canal informal.

**Pendência.** Validação técnica de como o campo é populado a partir do TOTVS, sob responsabilidade da equipe de Projetos Lincros.

### 4.3 Agendamento de Entrega

**Situação atual.** Cerca de 20 a 30% das entregas têm agendamento feito pela transportadora, sem participação do embarcador. A equipe perde controle do prazo prometido e não consegue separar atraso real de atraso justificado.

**Redesenho.** A equipe interna cria a instrução de agendamento no Lincros, valida a data com o cliente e envia para a transportadora pelo sistema. A ferramenta sobrescreve a previsão original com a data reagendada e mantém o histórico das duas, o que dá base documental para análise de SLA e para contestação quando aplicável.

### 4.4 Operação do Depósito Censos

**Situação atual.** A operadora interna se desloca à unidade para buscar romaneios físicos e dar baixa manual no sistema. Para solicitar agendamento de cargas dedicadas, usa um caminho à parte, fora do sistema. Ninguém na Schulz vê em tempo real o que sai do depósito.

**Redesenho.** O operador do Censos passa a ter usuário externo no Lincros, com perfil de baixa em tempo real e solicitação de agendamento de cargas dedicadas. A Schulz devolve para si a visibilidade sobre o que sai do depósito, e a operadora interna sai do papel de busca física de romaneios para assumir validação por exceção.

**Pendência.** Habilitação técnica do usuário externo, sob responsabilidade de Projetos Lincros e TI.

### 4.5 Regras Específicas por Destinatário

**Situação atual.** Clientes do Nordeste e outros segmentos exigem agendamento por período, ordem de chegada, ajudante, veículo específico ou paletização particular. A comunicação à transportadora vai solta, por e-mail ou telefone, com alta taxa de descumprimento e retrabalho.

**Redesenho.** As regras passam a ser cadastradas no Lincros como Instruções vinculadas ao destinatário. A cada embarque, o sistema dispara automaticamente as regras para a transportadora, junto com a documentação. O descumprimento passa a ter rastro documental, o que viabiliza responsabilização.

### 4.6 Integração TOTVS e Baixa de Embarque

**Situação atual.** O Romaneio é gerado no TOTVS, mas a baixa e o acompanhamento ficam dispersos. A operação roda em dois sistemas que não conversam no fluxo do dia a dia.

**Redesenho.** O Lincros consome a integração já existente com o Romaneio do TOTVS. A baixa é feita dentro do Lincros, encerrando o ciclo do embarque na mesma ferramenta em que o status é monitorado. O Romaneio do TOTVS vira o Embarque no Lincros, e essa unificação é pré-requisito para a auditoria de frete funcionar (capítulo 5).

### 4.7 Homologação de Transportadoras com Obrigação de Publicar Status

**Situação atual.** O processo de homologação de transportadoras conduzido por Compras não exige contratualmente que a transportadora publique ocorrências e status na ferramenta do embarcador. A consequência é uma torre incompleta, mesmo com o Lincros implantado.

**Redesenho.** A homologação passa a exigir, em contrato, que a transportadora publique ocorrências e status na plataforma da Schulz. Em um segundo momento, condicionar a liberação de pagamento à publicação dessas informações. Esse ponto é desenvolvido em detalhe no capítulo 6, porque é qualitativamente diferente dos outros seis: não é parametrização de sistema, é regra de negócio sobre a base de transportadoras.

---

## 5. A Linha que Divide Processo de Sistema

A análise das dores revela uma divisão importante entre o que se resolve por sistema (parametrização e automação) e o que depende de disciplina humana (processo). A confusão entre as duas dimensões é uma das causas mais comuns de implantação de TMS que entrega menos do que prometia.

### Sistema (parametrização e automação)

São tratados pelo Lincros, sem necessidade de mudança de comportamento, os seguintes pontos: cálculo automático do frete contra tabela cadastrada, auditoria de CT-e contra a tabela com tolerância configurável, geração de pré-fatura semanal automatizada para fracionado e lotação, painel de divergências com status, responsável e prazo, integração de CT-e para o ERP, e dashboards e KPIs em tempo real.

### Processo (disciplina operacional)

Dependem de disciplina humana e de definição interna os seguintes pontos: Romaneio obrigatório para toda saída física, aprovação de carga expressa via Ordem de Coleta no Lincros (em vez de e-mail e WhatsApp), aceite de pré-faturas pela transportadora via portal, data de saída obrigatória na nota fiscal antes da emissão, tratativa de divergência em até 48 horas com SLA contratual, e liberação financeira com pelo menos 5 dias de antecedência ao vencimento.

A Controladoria continua dona da auditoria. O que muda é o ferramental, que deixa de ser planilha e e-mail e passa a ser sistema com rastreabilidade nativa.

---

## 6. Governança da Malha de Transporte

Esta dimensão do projeto sustenta as outras seis. Ela é apresentada em capítulo próprio porque é qualitativamente diferente das demais e porque, sem ela, o ganho operacional do redesenho se deteriora ao longo do tempo.

### A natureza do problema

O Lincros é uma plataforma capaz de consolidar status de todas as transportadoras em uma única torre. Tecnicamente, está pronto para isso. Operacionalmente, depende de uma condição que não está no software: as transportadoras precisam alimentar o sistema com regularidade. Se uma parte da base não publica ocorrências, a torre fica parcialmente cega, e a Schulz acaba mantendo o esquema antigo de e-mail e WhatsApp em paralelo, anulando o ganho.

Essa publicação não acontece por iniciativa espontânea da transportadora. Ela acontece quando há condicionamento comercial. Hoje o processo de homologação conduzido por Compras avalia preço, prazo, capacidade e cobertura, mas não inclui a obrigação de uso da plataforma do embarcador como item contratual.

### O que o redesenho propõe

A homologação passa a incluir, como cláusula contratual, a obrigação da transportadora de publicar ocorrências e status na plataforma indicada pela Schulz. A formulação contratual deve prever o método (envio via EDI Proceda ou input manual no portal), os tipos de ocorrência mínimos exigidos, o prazo de publicação após o evento, e a consequência do descumprimento.

Em uma segunda fase, mais estratégica, a Schulz pode condicionar a liberação de pagamento de frete à publicação adequada das ocorrências do embarque correspondente. Esse mecanismo, conhecido em operações maduras como "no track, no pay", é o que dá tração real à governança e o que diferencia as operações que extraem valor de TMS daquelas que apenas o operam.

### Por que isso pertence ao escopo do projeto

Há uma tentação de tratar este ponto como exterior ao redesenho do processo de transporte, sob o argumento de que é "tema de Compras" ou "tema contratual". A análise das sete dores mostra que essa separação é artificial. As dores 1, 3 e 4 dependem da publicação de ocorrências para que o redesenho funcione na prática. As dores 2, 5 e 6 ganham robustez quando há cláusula contratual exigindo aderência a regras de cadastro e instruções. A dor 7, portanto, não é uma sétima dor isolada, é o ponto que sustenta as outras seis ao longo do tempo.

A recomendação técnica é que o trabalho de revisão da minuta de homologação seja conduzido em paralelo à fase de parametrização do Lincros, para que ambos entrem em vigor ao mesmo tempo.

---

## 7. Visão Comparativa por Área

A tabela abaixo consolida a transição AS IS para TO BE em cada área impactada pelo redesenho.

| Área | Situação atual | Redesenho |
|---|---|---|
| Vendas | Consulta 7 portais cerca de 10 vezes por dia | Torre única, atendimento por exceção |
| RVA | Acompanha coleta reversa por e-mail | Status fidedigno no Lincros via EDI Proceda |
| Compras | Aprova carga expressa por e-mail e WhatsApp | Aprova via Ordem de Coleta no sistema, com alçada definida |
| GAC | Agenda no TOTVS, comunica transportadora por e-mail | Embarque no Lincros, ordem automática para a transportadora |
| Expedição | Romaneio opcional | Romaneio obrigatório, vinculado à nota fiscal |
| Censos | Romaneios físicos, baixa manual | Usuário externo no Lincros, baixa em tempo real |
| Recebimento Fiscal | Lança CT-e manual, concilia natureza fiscal manualmente | CT-e integra ao ERP, natureza fiscal sugerida pelo sistema |
| Controladoria | Confere planilha, valida custos extras por e-mail | Painel de divergências com fluxo de tratativa |
| Financeiro | Recebe documentos com 3 dias do vencimento | Recebe com 10 a 20 dias, já auditado |

---

## 8. Princípios que Sustentam o Redesenho

Cinco princípios técnicos sustentam o desenho do projeto. Eles aparecem aqui de forma consolidada porque são transversais e atravessam mais de um capítulo.

**Cotação acontece antes da expedição.** O processo de cotação de carga expressa precisa ser concluído antes que a mercadoria saia da planta. Quando a transportadora já está com a carga, ela não está mais cotando, está impondo preço. Esse princípio não é funcionalidade do sistema, é regra de processo, e é uma das causas mais comuns de incremento de custo evitável em operações com cotação ativa.

**Mínimo de três transportadoras na cotação.** Para que a cotação spot seja efetivamente competitiva, ela precisa acionar pelo menos três transportadoras homologadas. Abaixo desse número, o que existe é simulação de comparação. O Lincros suporta o agrupamento de transportadoras por perfil e por região, o que facilita a aplicação consistente desse princípio.

**Padrão EDI Proceda como linguagem comum da malha.** A torre única só funciona se há uma linguagem comum entre as transportadoras. O EDI Proceda já está estabelecido no mercado e é suportado pela maior parte das transportadoras de porte. Para as que não têm capacidade técnica imediata, o input manual no portal Lincros é alternativa viável, complementada pelo de/para de ocorrências configurado por transportadora.

**Cubagem parametrizada por transportadora.** Cada transportadora cobra peso de forma diferente (peso bruto, peso cubado, fator próprio). Sem parametrização da regra de cobrança de cada uma na ferramenta, o sistema gera divergência falsa em volume, e a equipe perde tempo conferindo o que não é divergência real. Esse ajuste é pré-requisito da auditoria automatizada.

**Integração antecipada da fatura.** O Financeiro hoje pede 3 dias úteis antes do vencimento. Com a auditoria automatizada e o monitoramento de entrega funcionando, recomenda-se integrar a fatura entre 10 e 20 dias antes do vencimento. Isso amplia a janela de tratativa de divergências e reduz a pressão sobre a Controladoria, sem mudar o calendário de pagamento.

---

## 9. Pendências e Próximos Passos

### Pendências técnicas em aberto

- Validação de como o campo de endereço de entrega é populado a partir do TOTVS para alimentar o Lincros (Dor 4.2). Responsável: Projetos Lincros.
- Habilitação do usuário externo Censos no Lincros, com perfil de baixa em tempo real e solicitação de cargas dedicadas (Dor 4.4). Responsáveis: Projetos Lincros e TI Schulz.
- Revisão da minuta de homologação de transportadoras para incluir cláusula de publicação de ocorrências (capítulo 6). Responsável: Compras.

### Sequência sugerida de implantação

A fase de parametrização do Lincros e a fase de revisão contratual da homologação devem rodar em paralelo, com data alvo única de entrada em vigor. Isso garante que, quando a torre operacional estiver completa do ponto de vista técnico, a base de transportadoras já esteja contratualmente obrigada a alimentá-la.

A sequência interna recomendada é:

1. Parametrização das tabelas de frete por transportadora, incluindo regra de cubagem.
2. Integração TOTVS para Romaneio e CT-e.
3. Habilitação do usuário externo Censos.
4. Configuração do de/para de ocorrências EDI Proceda por transportadora.
5. Ativação do fluxo de Ordem de Coleta para carga expressa.
6. Ativação do painel de divergências para a Controladoria.
7. Entrada em vigor da nova cláusula de homologação para transportadoras renovadas e novas.
8. Revisão das transportadoras já contratadas, com aditivo de cláusula de publicação.

### Indicadores de acompanhamento

Para a fase pós-implantação, são propostos os seguintes indicadores de acompanhamento, de leitura mensal:

- Percentual de embarques com status publicado pela transportadora dentro do prazo.
- Tempo médio entre ocorrência e publicação da informação no Lincros.
- Volume de divergências de auditoria identificadas pelo sistema, por categoria.
- Saving realizado em auditoria de frete, com evidência de cobrança a maior contestada.
- Tempo médio entre integração da fatura e liberação para pagamento.

---

## Anexos

### Anexo A. Notas da Reunião de Mapeamento (18/03/2026)

**Local:** Schulz S.A., Joinville/SC
**Modalidade:** Presencial
**Estrutura da agenda:**

| Bloco | Horário | Duração |
|---|---|---|
| Abertura Lincros | 9h-9h15 | 15 min |
| Logística (Carlos Dias) | 9h15-12h | bloco completo |
| Compras (Eduardo Bertolotti) | 9h45-10h15 | 30 min |
| Fiscal (Anselmo) | 10h15-10h45 | 30 min |
| Financeiro (Vitor) | 10h45-11h15 | 30 min |
| Controladoria (Luciana) | 11h15-11h45 | 30 min |
| TIC (Gerson, Sidnei, Ricardo, Cláudio) | 9h-12h | bloco completo |

**Participantes registrados por área:**

- Logística: Edgar (coordenador), Rodrigo (analista de inventário), Jackson (analista de CD), Elenilson (especialista PCP), Lincon (gerente de Compressores). Carlos Dias, gerente de Logística da Automotiva, não participou.
- Compras: Cida e Denise.
- Financeiro: Vitor (gerente) e Eduardo (analista).
- Controladoria: Luciana (gerente) e Maiara (analista).
- TIC: Gustavo (Revenda Reversa), Claudemir (Revenda), João (Manutenção).

### Anexo B. Glossário Técnico

**CT-e.** Conhecimento de Transporte Eletrônico, documento fiscal emitido pela transportadora.

**Cubagem.** Cálculo de peso baseado em volume, usado quando o produto é leve mas ocupa muito espaço. Cada transportadora aplica fator próprio.

**EDI Proceda.** Padrão de troca eletrônica de dados estabelecido no mercado de transporte brasileiro, usado para envio de ocorrências e status de entrega entre transportadoras e embarcadores.

**Embarque (Lincros).** Equivalente ao Romaneio do ERP, é a unidade de gestão do transporte dentro do TMS.

**EDI (em geral).** Eletronic Data Interchange, troca eletrônica de dados estruturados entre sistemas.

**FOB.** Free On Board. O destinatário é responsável pelo frete e pela coordenação da coleta.

**CIF.** Cost, Insurance and Freight. O embarcador é responsável pelo frete até o destino.

**GAC.** Setor de agendamento da Schulz, responsável por montar a programação de coletas.

**Ordem de Coleta.** Instrumento sistêmico do Lincros usado para acionamento de carga expressa, com peso, valor, destino, prazo e modalidade já vinculados.

**Pré-fatura.** Documento gerado pelo Lincros que agrupa CT-es aptos para pagamento e dispara EDI para a transportadora confirmar.

**Romaneio (TOTVS).** Documento interno que organiza a relação de itens de um embarque.

**Tabela de frete.** Acordo prévio entre embarcador e transportadora que define preço por origem, destino e modalidade de veículo.

**TMS.** Transportation Management System, sistema de gestão de transporte. No caso da Schulz, o TMS é o Lincros.

**Tolerância configurável.** Margem de aceitação automática de divergência (em valor ou percentual) parametrizada por transportadora.

### Anexo C. Histórico de Versões

- **V1 (presente):** Documento mestre integrado, abril de 2026.
- Versões anteriores do diagnóstico foram produzidas em formato de apresentação (V2 e V3) e estão arquivadas internamente.

---

*Documento elaborado pela Consolida em parceria com Lincros para a Schulz S.A. Distribuição interna autorizada.*
