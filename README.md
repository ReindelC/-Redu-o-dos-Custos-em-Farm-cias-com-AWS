# -Redução-dos-Custos-em-Farmácias-com-AWS
Desafio DIO  Redução dos Custos em Farmácias com AWS

# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇ0S AWS

Data: [21/05/2026]
Empresa: Abstergo Industries 
Responsável: [Cristiane]

## Introdução
Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por Cristiane. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos.

## Descrição do Projeto
O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos especÃ­ficos. A seguir, serão descritas as etapas do projeto:

1️⃣ AWS Cost Explorer + AWS BudgetsVantagens para farmácia:
Identifica picos de gastos em horários de menor movimento (se usar recursos 24/7 sem necessidade)
Cria alertas automáticos quando o custo ultrapassa o orçamento mensal
Recomenda Savings Plans e Reserved Instances — farmácias com cargas de trabalho previsíveis (ex: sistema PDV, gestão de estoque) podem economizar até 72% trocando On-Demand por Reserved
Como obter:
Já vem habilitado na conta AWS (sem custo adicional)
Acesse: Console AWS → Cost Explorer → criar orçamentos por serviço ou tag
Use tags para marcar recursos por loja/unidade e identificar desperdícios

2️⃣ AWS Compute OptimizerVantagens para farmácia:
Analisa servidores EC2 e sugere dimensionamento correto (rightsizing)
Farmácias costumam superdimensionar servidores de sistemas legados (ex: ERP, gestão de receitas) — o Compute Optimizer recomenda redução de instância sem perder performance
Suporte a instâncias Graviton (ARM), que custam ~20% menos que x86 equivalentes
Como obter:
Ativar no Console AWS → Compute Optimizer → "Opt in"
Ele analisa as últimas 2 semanas de uso e gera recomendações
Aderir às recomendações com 1 clique (modificar instância)

3️⃣ Amazon S3 Intelligent-Tiering + S3 Lifecycle PoliciesVantagens para farmácia:
Farmácias acumulam muitos dados: notas fiscais eletrônicas, relatórios de estoque, imagens de prescrições, backups de sistemas
Intelligent-Tiering move automaticamente objetos entre camadas de armazenamento conforme o acesso — dados pouco acessados vão para camadas mais baratas sem intervenção manual
Lifecycle Policies permitem migrar logs e backups antigos para S3 Glacier (armazenamento de longo prazo até 90% mais barato)
Ideal para compliance (ANVISA exige retenção de documentos por prazos específicos)
Como obter:
Criar bucket S3 → habilitar Intelligent-Tiering
Configurar regras de ciclo de vida: API, CloudFormation ou Console AWS
Exemplo prático: mover backups com mais de 90 dias para S3 Standard-IA, e com mais de 365 dias para S3 Glacier


## Conclusão
A implementação de ferramentas AWS gera redução dos custos mas sem diminuir performance — pagando apenas pelo realmente necessário, com alertas para evitar desperdícios e automação para dados que não precisam mais de armazenamento caro.


💰 Não é apenas economia isolada em cada serviço — é um ciclo de otimização contínua. O Cost Explorer mostra onde gastar menos, o Compute Optimizer ajusta o que está rodando, e o S3 arquiva o que não precisa mais ser rápido. Uma ferramenta valida e potencializa a outra.
