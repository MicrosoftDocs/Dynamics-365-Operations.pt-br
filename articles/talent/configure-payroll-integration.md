---
title: Configurar a integração da folha de pagamento entre o Talent e o Dayforce
description: Este tópico explica como configurar a integração entre o Microsoft Dynamics 365 for Talent e o Ceridian Dayforce para processar um ciclo de pagamento.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9a88bf61dbb12520b555ceb7363b1c646d95386e
ms.sourcegitcommit: 204e4554e409c39fbbf7b273ad138ce2809931a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2019
ms.locfileid: "898435"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a>Configurar a integração da folha de pagamento entre o Talent e o Dayforce

[!include [banner](includes/banner.md)]

A integração entre o Microsoft Dynamics 365 for Talent e o Ceridian Dayforce depende de várias etapas de configuração descritas neste tópico. Você deve configurar a integração no Talent e no Dayforce antes de poder processar uma execução de pagamento.

Ao usar um serviço como o Dayforce para concluir execuções de pagamento, é necessário ativar a integração no Talent. A integração requer dados específicos do Talent. Portanto, você deve verificar se os dados mapeados para o Dayforce estão configurados no Talent de forma compatível com a integração. A integração usa as seguintes categorias amplas de dados:

- Dados de recursos humanos
- Dados de remuneração
- Dados da folha de pagamento, como ciclos de pagamento, períodos de pagamento e códigos de ganhos
- Dados do trabalhador

Este tópico descreve as etapas que você deve seguir para ativar a integração. Também explica os tipos de dados e os detalhes de configuração que a integração requer.

## <a name="enable-the-integration"></a>Habilitar a integração

No Talent, você deve ativar a integração e inserir as informações de configuração para se conectar ao Dayforce. Para que a transação da contabilidade que for produzida seja importada para o Microsoft Dynamics 365 for Finance and Operations, também é preciso configurar uma conta de armazenamento do Microsoft Azure e inserir a cadeia de conexão do Armazenamento do Azure no Finance and Operations.

Para ativar a integração no Talent, siga as etapas a seguir.

1. Na página **Administração do sistema**, selecione **Configuração de integração**.
2. Digite o ponto de extremidade seguro do File Transfer Protocol (FTP) e o caminho seguro da pasta FTP.
3. Digite o nome e a senha do usuário que acessará o ponto de extremidade e o caminho da pasta seguros do FTP.
4. Teste a conexão, conforme necessário, e defina a opção **Habilitar integração da folha de pagamento** como **Sim**.

Quando a integração é ativada, o pacote e os arquivos de exportação de dados são criados e a frequência é configurada. Você pode alterar essa frequência conforme necessário.

Para obter mais informações sobre as contas de armazenamento do Azure e as cadeias de conexão do Armazenamento do Azure, consulte os seguintes tópicos do Azure:

- [Sobre as contas de armazenamento do Azure](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [Configurar cadeias de conexão do Armazenamento do Azure](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

## <a name="configure-your-data"></a>Configurar seus dados 

Para processar a folha de pagamento, você deve configurar dados de RH no Talent. Você deve configurar dados organizacionais, como cargos e posições, juntamente com informações sobre benefícios e remuneração. Esses dados fornecem as informações de emprego, pagamento e dedução necessárias para gerar o pagamento do empregado.

### <a name="human-resource-data"></a>Dados de RH

#### <a name="benefits"></a>Benefícios 

O RH fornece ferramentas para a configuração e manutenção dos benefícios, deduções e planos de remuneração do trabalhador que uma organização oferece ou processa para seus funcionários.

Ao criar benefícios, tenha em mente os dados e configurações a seguir usados no Dayforce.

##### <a name="benefit-plans"></a>Planos de benefícios

- Plano (obrigatório)
- Tipo (obrigatório)
- Impacto da folha de pagamento (obrigatório)
- Recuperar atrasos de pagamento
- Método de dedução
- Prioridade da dedução
- Limitar período
- Valor de limite

##### <a name="benefits"></a>Benefícios

- Plano (obrigatório)
- Tipo (obrigatório)
- Opção (obrigatória)
- ID do benefício (obrigatória)
- Frequência
- Base
- Valor ou taxa
- Código de ganhos

##### <a name="supported-frequencies"></a>Frequências com suporte 

- Semanalmente
- Por quinzena
- Quinzenal
- Mensalmente

##### <a name="supported-bases"></a>Bases com suporte 

- Valor fixo
- Percentual de ganhos
- Horas produtivas

O Dayforce cria as deduções a seguir, com base no impacto da folha de pagamento definido no plano de benefícios.

| Seleção no Talent        | Resultado no Dayforce                            |
|----------------------------|-----------------------------------------------|
| Nenhum(a)                       | Nenhuma dedução é criada.                      |
| Somente dedução             | Uma dedução de funcionário é criada.             |
| Somente contribuição          | Uma dedução de empregador é criada.             |
| Dedução e contribuição | Deduções de funcionário e empregador são criadas. |

Para obter mais informações sobre como definir e gerenciar um programa de benefícios, consulte os seguintes tópicos:

- [Entregar um programa de benefícios do funcionário](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [Criar um novo benefício](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [Definir regras e políticas de qualificação para o benefício](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [Inscrever e remover benefícios de trabalhadores](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a>Remuneração 

O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios. Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos. O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável.

O Dayforce usa informações de remuneração para calcular a taxa por hora ou anual de um funcionário. Planos de remuneração fixa e conversões de taxa de pagamento são necessários. Os funcionários devem estar associados a um plano de remuneração fixa.

Para obter mais informações sobre planos de remuneração, veja os tópicos a seguir:

- [Criar planos de remuneração fixa](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [Criar planos de remuneração variável](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [Desenvolver estrutura e planos de remuneração/salário](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [Processar remuneração](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [Definir processo de remuneração e calcular resultados](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [Inscrever um funcionário em um plano de remuneração fixa](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [Inscrever um funcionário em um plano de remuneração variável](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a>Trabalhos 

Um trabalho é um conjunto de tarefas e responsabilidades exigidas de uma pessoa que realiza um trabalho. Para obter mais informações, consulte os seguintes tópicos:

- [Configurando os componentes de um trabalho](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [Definir novos trabalhos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a>Posições

Um cargo é uma instância individual de um trabalho. Por exemplo, a posição "Gerente de vendas (Leste)" é uma das posições associadas ao trabalho "Gerente de vendas". Uma posição existe em um departamento. Apenas um trabalhador pode ser associado a cada posição.

Considere os seguintes dados e configurações ao configurar as posições:

- Posição (obrigatória)
- Descrição (obrigatória)
- Trabalho (obrigatório)
- Departamento (obrigatório)
- Tipo de posição (obrigatório)
- Equivalente ao horário integral
- Horas normais anuais (obrigatórias)
- Pago por entidade legal (obrigatório)
- Ciclo de pagamento (obrigatório)
- Dimensão financeira padrão – Centro de custo (obrigatório)
- Atribuição do trabalhador – Trabalhador, início da atribuição, fim da atribuição, código de motivo

Se várias posições no mesmo departamento estiverem associadas ao mesmo trabalho, elas serão consolidadas em uma única posição no Dayforce.

Para obter mais informações, consulte os seguintes tópicos:

- [Organizar sua força de trabalho usando departamentos, trabalhos e posições](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [Configurar posições](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a>Departamentos

Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização. Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos. Você pode usar departamentos para relatar áreas funcionais. Os departamentos podem ter a responsabilidade de lucros e perdas.

Para obter mais informações, consulte os seguintes tópicos:

- [Criar um departamento e associá-lo à hierarquia de departamentos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [Definir novos departamentos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a>Ciclos de pagamento e períodos de pagamento

Um ciclo de pagamento determina a frequência com que a folha de pagamento é executada e os dias específicos em que os trabalhadores são pagos. Por exemplo, um ciclo de pagamento pode ser mensal e os funcionários podem ser pagos no último dia do mês. Como alternativa, um ciclo de pagamento pode ser semanal e os funcionários podem ser pagos na terça-feira após o término do período de pagamento. Ciclos de pagamento são atribuídos a posições para controlar quando os trabalhadores nessas posições são pagos.

Após a criação dos ciclos de pagamento, você pode gerar períodos de pagamento para cada ciclo. Cada período de pagamento inclui uma data de pagamento padrão baseada nas informações que você fornece. No entanto, você pode modificar a data de pagamento padrão em um período de pagamento para permitir exceções (por exemplo, quando a data de pagamento cai em um feriado).

As seguintes informações são usadas no Dayforce:

- Ciclo de pagamento (obrigatório)
- Frequência do ciclo de pagamento (obrigatória)
- Data de início do período (primeiro período de pagamento obrigatório)
- Data de pagamento padrão (primeiro período de pagamento obrigatório)

Essas informações são integradas ao Dayforce como grupos de pagamento e são separadas por país ou região para cada ciclo de pagamento. Pelo menos um período de pagamento deve ser gerado antes da integração. O Dayforce gera datas de pagamento e calendários do grupo de pagamento, com base na data de início do primeiro período de pagamento e na data de pagamento padrão configurada no Talent.

#### <a name="earning-codes"></a>Códigos de ganhos

Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem. Os códigos têm vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.

As seguintes informações são usadas no Dayforce:

- Código de ganhos (obrigatório)
- descrição
- Unidade de medida
- Produtivo

### <a name="worker-data"></a>Dados do trabalhador

Os registros dos vários tipos de trabalhadores que você tem são importantes para o RH e sistemas de folha de pagamento. As informações inseridas podem ser usadas para rastrear trabalhadores e informações pessoais.

Você pode manter estas informações para trabalhadores:

- **Básicas** – mantenha informações básicas do trabalhador, como informações de contato, demográficas, de identificação, sobre a família, o status de serviço militar, informações de exilado, contatos pessoais e de emergência.
- **Emprego** – mantenha informações sobre o emprego dos trabalhadores, como a afiliação da empresa ou organização, a atribuição de posição, as datas inicial e final, a qualificação para trabalho, o contrato de trabalho, a pensão, férias e as informações de mudança.
- **Licença e ausência** – mantenha informações sobre as ausências dos trabalhadores, como o calendário de trabalho, as transações de ausência e a configuração de ausência.
- **Remuneração e folha de pagamento** – mantenha informações sobre os planos de remuneração e as informações de folha de pagamento de trabalhadores, como o registro do plano, prêmios, o desempenho, a comissão, informações sobre impostos, aposentadoria e deduções do salário.

Ao inserir informações do trabalhador, tenha em mente os dados e configurações a seguir usados no Dayforce.

#### <a name="general-information"></a>Informações gerais

- Número de equipe (obrigatório)
- Nome (obrigatório)
- Sobrenome (obrigatório)
- Nome do meio
- Aniversário de tempo de serviço
- Conhecido como

#### <a name="personal-information"></a>Informações pessoais

- Estado civil (obrigatório)
- Data de nascimento (obrigatória)
- Sexo (obrigatório)
- Pessoa portadora de deficiências
- Região do país de nacionalidade (somente para o México)

#### <a name="address-information"></a>Informações de endereço

- Principal (obrigatório)
- País/região (obrigatório)
- CEP (obrigatório)
- Número da rua (obrigatório) (somente para o México)
- Complemento do edifício (somente para o México)
- Cidade (obrigatória)
- Estado (obrigatório)
- Município (obrigatório)

#### <a name="contact-information"></a>Informações de contato 

- Principal (obrigatório)
- Número de contato (obrigatório)
- Extensão

#### <a name="payroll-information-and-earning-codes"></a>Informações sobre folha de pagamento e códigos de ganhos

Os funcionários podem receber ganhos específicos com uma determinada frequência de pagamento e ter um método de pagamento preferencial. Os campos a seguir são usados no Dayforce para ajudar a garantir que essas preferências e configurações sejam usadas.

##### <a name="earning-codes"></a>Códigos de ganhos

- Posição (obrigatória)
- Código de ganhos (obrigatório)
- Frequência (obrigatória)
- Valor (obrigatório)

##### <a name="payroll-information"></a>Informações da folha de pagamento

- Método de Pagamento
- Região econômica (obrigatória)
- ID de Benefícios do Funcionário
- Número de ID nacional (obrigatório)
- Número de serviço militar
- ID de turno (obrigatória)
- Número fiscal (obrigatório)
- ID do sindicato (obrigatória)
- ID do dia útil (obrigatória)
- Número de autorização de trabalho

> [!NOTE]
> Para o método de pagamento, o México permite **Pagamento à vista**, **Cheque** (o cheque físico da empresa) e **Pagamento Eletrônico**. Se nenhum método de pagamento for especificado, **Cheque** é usado por padrão.

#### <a name="employment-details"></a>Detalhes do emprego

O histórico de detalhes de emprego é usado como principal informação para derivar os status de contratação, rescisão e recontratação de um funcionário no Dayforce. O Dayforce suporta apenas um registro de emprego ativo de cada vez.

- Data de início do emprego (obrigatória)
- Data final do emprego
- Data de início
- Data inicial ajustada
- Data de rescisão (obrigatória após a rescisão)
- Motivo da rescisão (obrigatória após a rescisão)

As principais datas de um funcionário são derivadas usando-se as informações a seguir.

| Talent                | Dayforce                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| Data de contratação mais recente | Início de emprego do registro histórico de emprego atual não terminado                                 |
| Data da rescisão      | Data de rescisão do registro histórico de emprego atual não terminado                                 |
| Data de início            | Data de início ajustada, data de início ou início de emprego do registro histórico de emprego não ativo atual |
| Data original de contratação    | Início de emprego do registro histórico de emprego mais antigo                                               |

#### <a name="compensation"></a>Remuneração

Um plano de remuneração fixa deve estar associado à posição principal de cada funcionário durante um período de emprego. Esse período tem início na data em que o funcionário foi contratado (ou na data de início do emprego) e continua até a rescisão.

- Data de vigência (obrigatória)
- Data de validade
- Taxa de pagamento (obrigatória)
- Conversões de taxa de pagamento (obrigatórias)
- Equivalente anual (obrigatório)
- Equivalente por hora (obrigatório)

Se um funcionário por hora tiver várias posições, a remuneração fixa da posição principal é importada para o Dayforce como a taxa base/salário do nível do funcionário. Para posições não principais, a taxa por hora é salva na posição correspondente no Dayforce.

Se um funcionário assalariado tiver várias posições, a taxa acumulada de horas e o salário anual em todas as posições ativas serão derivados e usados como a taxa base/salário do nível do funcionário.

#### <a name="identification-numbers"></a>Números de identificação

##### <a name="social-security-identifier"></a>Cadastro de Pessoa Física (CPF) 

Todos os funcionários devem ter um identificador principal. Esse identificador deve ser o tipo de identificação **CPF**. No Dayforce, ele é derivado automaticamente como o identificador de pessoa física do funcionário necessário para a contratação.

- Principal (obrigatório)
- Tipo de identificação = "CPF"
- Data da emissão
- Data de Vencimento

Os funcionários podem declarar vários números de identificação do tipo de identificação **CPF**. No entanto, somente o registro marcado como **Principal** será integrado ao Dayforce, independentemente de o número estar ativo ou expirado.

#### <a name="bank-accounts-and-disbursements"></a>Contas bancárias e pagamentos

Informações de conta bancária válidas devem ser inseridas para qualquer funcionário que opte por ser pago por meio de transferências bancárias.

| Talent                         | Dayforce                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| Número da conta bancária (obrigatório) |                                                                                                             |
| Código SWIFT (obrigatório)          | Campo **ID do banco** usado no processamento da folha de pagamento no México.                                                             |
| Número da agência (obrigatório)       |                                                                                                             |
| Tipo de conta bancária (obrigatório)   | Campo **Tipo de conta** usado no processamento da folha de pagamento no México. Os valores com suporte incluem **Movimento** e **Folha de pagamento**. |

> [!NOTE]
> Os funcionários que optarem por serem pagos por meio de transferências bancárias deverão fornecer um link para uma conta de pendência em uma entidade legal que tenha seu endereço principal no México e esteja associada a uma conta bancária válida de um banco mexicano. Todas as outras contas que não são de pendência são ignoradas.

#### <a name="address-information"></a>Informações de endereço

Todos os funcionários devem ter um local principal. No Dayforce, esse local é usado para determinar a residência principal do funcionário para fins fiscais.

- Principal (obrigatório)
- País/região (obrigatório)
- CEP (obrigatório)
- Rua (obrigatória)
- Número da rua (obrigatório)
- Complemento do edifício
- Cidade (obrigatória)
- Estado (obrigatório)
- Município (obrigatório)

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a>Configurar seus dados para gerar folha de pagamento nos Estados Unidos e no Canadá

Se você está gerando pagamento para funcionários nos Estados Unidos e no Canadá, os seguintes elementos devem ser configurados:

- Departamentos são necessários em posições.
- Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.

> [!NOTE] 
> Você pode configurar o Talent para exigir que Posições especifique um Departamento. Para isso, acesse **Posições Compartilhadas de Recursos Humanos > Posições > Exigir departamentos nas posições**. Recomendamos que esta configuração seja imposta para a integração.

### <a name="job-types"></a>Tipos de trabalho

Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias. Os tipos de trabalho são necessários para processar a folha de pagamento nos Estados Unidos e no Canadá. Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora. Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.

Os seguintes tipos de trabalho e descrições são obrigatórios.

| Tipo de trabalho   | descrição |
|------------|-------------|
| Por hora     | Por hora      |
| Assalariado   | Assalariado    |

### <a name="position-types"></a>Tipos de posição 

Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza. Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.

Os seguintes tipos de posição e descrições são obrigatórios.

| Tipo de posição   | descrição        |
|-----------------|--------------------|
| Horário integral       | Funcionário de tempo integral |
| Meio período       | Funcionário de meio período |

### <a name="reason-codes"></a>Códigos de motivos

Códigos de motivo fornecem informações sobre o status de um funcionário. Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.

Os seguintes códigos de motivo e descrições são obrigatórios.

| Código de motivo    | descrição      | Cenários aplicáveis |
|----------------|------------------|----------------------|
| DEMISSÃO    | Demissão      | Demitir trabalhador     |
| TERMINATION    | Finalização      | Demitir trabalhador     |
| RETIREMENT     | Aposentadoria       | Demitir trabalhador     |
| OTHER          | Outros motivos    | Demitir trabalhador     |
| DEATH          | Morte            | Demitir trabalhador     |
| LEAVEOFABSENCE | Licença | Demitir trabalhador     |
| CONTRACTEND    | Fim do contrato  | Demitir trabalhador     |
| SALARYCHANGE   | Alteração de salário | Remuneração         |

### <a name="marital-status"></a>Estado civil

Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.

A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.

| Talent                 | Dayforce             |
|------------------------|----------------------|
| Casado(a)                | Casado(a)              |
| Única                 | Única               |
| Viúvo(a)                | Viúvo(a)              |
| Divorciado(a)               | Divorciado(a)             |
| Parceria Registrada | Parceiro doméstico |
| Nenhum(a)                   | Nenhum(a)                 |
| Coabitando             | Coabitando           |

### <a name="gender"></a>Sexo

As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.

A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.

| Talent       | Dayforce        |
|--------------|-----------------|
| Masculino         | Masculino            |
| Feminino       | Feminino          |
| Não específico | *Sem suporte* |

### <a name="earning-codes"></a>Códigos de ganhos

Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem. Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto. Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.

#### <a name="supported-frequencies"></a>Frequências com suporte

- Todas
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Endereços

A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer. Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.

| Talent          | Dayforce              |
|-----------------|-----------------------|
| País/Região  | Código do País          |
| CEP | CEP           |
| Estadual           | Código de estado            |
| Cidade            | Cidade                  |
| Região          | Município (municipalidade) |
| Rua          | Linha de endereço 1        |

### <a name="tax-regions"></a>Regiões fiscais

Regiões fiscais são usadas para determinar os impostos apropriados a serem aplicados durante a geração da folha de pagamento. As regiões fiscais são mapeadas para o Dayforce como endereços de localização. A região fiscal padrão deve estar associada à posição ativa do trabalhador. 

- Região fiscal (obrigatória)
- País/região (obrigatório)
- Estado (obrigatório)
- Região 
- Cidade (obrigatória)

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a>Configurar seus dados para gerar folha de pagamento no México

Se você está gerando pagamento para funcionários no México, os seguintes elementos devem ser configurados:

- Departamentos são necessários em posições.
- Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.

### <a name="job-types"></a>Tipos de trabalho

Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias. Tipos de trabalho são necessários para processar a folha de pagamento no México. Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora. Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.

Os seguintes tipos de trabalho e descrições são obrigatórios.

| Tipo de trabalho   | descrição |
|------------|-------------|
| Por hora     | MX por hora   |
| Assalariado   | MX assalariado |

### <a name="position-types"></a>Tipos de posição 

Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza. Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.

Os seguintes tipos de posição e descrições são obrigatórios.

| Tipo de posição   | descrição        |
|-----------------|--------------------|
| Horário integral       | Funcionário de tempo integral |
| Meio período       | Funcionário de meio período |

### <a name="reason-codes"></a>Códigos de motivos

Códigos de motivo fornecem informações sobre o status de um funcionário. Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.

Os seguintes códigos de motivo e descrições são obrigatórios.

| Código de motivo            | descrição                    | Cenários aplicáveis |
|------------------------|--------------------------------|----------------------|
| DEPARTUREBEFOREPAYMENT | Partida antes da primeira folha de pagamento | Demitir trabalhador     |
| RESIGNATION            | Demissão                    | Demitir trabalhador     |
| PENSION                | Aposentadoria                        | Demitir trabalhador     |
| TERMINATION            | Finalização                    | Demitir trabalhador     |
| RETIREMENT             | Aposentadoria                     | Demitir trabalhador     |
| ABSENTEE               | Absentista                       | Demitir trabalhador     |
| OTHER                  | Outros motivos                  | Demitir trabalhador     |
| CLOSURE                | Fechamento da empresa               | Demitir trabalhador     |
| DEATH                  | Morte                          | Demitir trabalhador     |
| LEAVEOFABSENCE         | Licença               | Demitir trabalhador     |
| CONTRACTEND            | Fim do contrato                | Demitir trabalhador     |
| SALARYCHANGE           | Alteração de salário               | Remuneração         |

### <a name="terms-of-employment"></a>Contrato de trabalho

Termos de emprego são usados para criar categorias de termos de emprego. Os termos são mapeados para o Dayforce como valores de indicador de emprego.

Os termos de emprego e as descrições a seguir são obrigatórios.

| Contrato de trabalho   | descrição |
|-----------------------|-------------|
| Normal               | Normal     |
| Direto                | Direto      |
| Estágio            | Estágio  |
| Permanente             | Permanente   |

### <a name="marital-status"></a>Estado civil

Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.

A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.

| Talent                 | Dayforce                  |
|------------------------|---------------------------|
| Casado(a)                | Casado(a)                   |
| Única                 | Única                    |
| Viúvo(a)                | Viúvo(a)                   |
| Divorciado(a)               | Divorciado(a)                  |
| Parceria Registrada | Parceiro doméstico      |
| Nenhum(a)                   | *Não há suporte para o México* |
| Coabitando             | *Não há suporte para o México* |

### <a name="gender"></a>Sexo

As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.

A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.

| Talent       | Dayforce                  |
|--------------|---------------------------|
| Masculino         | Masculino                      |
| Feminino       | Feminino                    |
| Não específico | *Não há suporte para o México* |

### <a name="payment-method"></a>Forma de pagamento

Os métodos de pagamento dão ao funcionário e à empresa uma maneira de descrever como os funcionários serão pagos. Os métodos de pagamento são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.

A tabela a seguir mostra como os métodos de pagamento são mapeados para o Dayforce.

| Talent             | Dayforce                  |
|--------------------|---------------------------|
| Pagamento à vista               | Pagamento à vista                      |
| Pagamento eletrônico | Transferência                  |
| Verificação              | Cheque                    |
| Boleto bancário         | *Não há suporte para o México* |
| Outros              | *Não há suporte para o México* |

### <a name="bank-account-type"></a>Tipo de conta bancária

Os tipos de conta bancária são usados para pagamentos eletrônicos aos funcionários. Os tipos de conta bancária são mapeados para o Dayforce como informações da conta de transferência. Os tipos de conta bancária são convertidos, conforme apropriado, nos valores aceitos após a integração.

| Talent            | Dayforce                  |
|-------------------|---------------------------|
| Conta corrente  | CheckingAccount           |
| Conta-salário   | PayrollAccount            |
| Conta de poupança   | *Não há suporte para o México* |
| Conta BankGirot | *Não há suporte para o México* |
| Conta PlusGirot | *Não há suporte para o México* |

### <a name="earning-codes"></a>Códigos de ganhos

Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem. Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto. Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.

#### <a name="supported-frequencies"></a>Frequências com suporte

- Todas
- EVERYPAY
- EACHPAYPERIOD
- EVRYOTHRPAYODD
- EVRYOTHRPAYEVN
- 1OFMTH
- LASTOFMTH
- 2OFMTH
- 3OFMTH
- 4OFMTH
- 5OFMTH
- 1N2OFMTH
- 3N4OFMTH
- 1N3OFMTH
- 1N4OFMTH
- 2N3OFMTH
- 2N4OFMTH
- 1N2N3OFMTH
- 1N2N4OFMTH
- 1N3N4OFMTH
- 2N3N4OFMTH
- 1N2N3N4OFMTH - 1N2N3N4OFMTH
- 2N3N4N5OFMth - 2N3N4N5OFMth
- 1OFQTR - 1OFQTR
- LASTOFQTR – LASTOFQTR
- LASTMTHOFQTR – LASTMTHOFQTR
- 1OFYEAR - 1OFYEAR
- LASTOFYEAR – LASTOFYEAR
- NOVNDECOFYEAR - NOVNDECOFYEAR

### <a name="addresses"></a>Endereços

A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer. Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.

| Talent              | Dayforce              |
|---------------------|-----------------------|
| País/Região      | Código do País          |
| CEP     | CEP           |
| Estadual               | Código de estado            |
| Cidade                | Cidade                  |
| Região              | Município (municipalidade) |
| Rua              | Linha de endereço 1        |
| Número       | Linha de endereço 2        |
| Complemento do edifício | Linha de endereço 5        |

### <a name="passport-number"></a>Número do passaporte

Os funcionários podem declarar as informações do passaporte. Essas informações são do tipo de identificação **Passaporte** e estão integradas ao Dayforce como parte das informações específicas do México de um funcionário.

- Tipo de identificação = "Passaporte"
- Data da emissão
- Data de Vencimento

Os funcionários podem declarar vários números de identificação do tipo de identificação **Passaporte**. No entanto, apenas a entrada atual do passaporte ativo é integrada ao Dayforce. Se todas as entradas do passaporte expirarem, o passaporte emitido mais recentemente será integrado ao Dayforce.
