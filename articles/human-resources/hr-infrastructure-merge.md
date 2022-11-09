---
title: Visão geral de mesclagem de infraestrutura do Dynamics 365 Human Resources
description: Este artigo descreve a mesclagem de infraestrutura do Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f79ef3ed5db7583eb44b99e49c010778ce8524d1
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733431"
---
# <a name="dynamics-365-human-resources-infrastructure-merge"></a>Mesclagem de infraestrutura do Dynamics 365 Human Resources 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="dynamics-human-resources-365"></a>Dynamics Human Resources 365

O Microsoft Dynamics 365 Human Resources fornece ferramentas que ajudam as equipes de RH a aumentar a agilidade organizacional, transformar a experiência do funcionário e otimizar os programas de RH para criar um local de trabalho onde as pessoas e a empresa possam prosperar. Para saber mais sobre o Dynamics 365 Human Resources, consulte [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Transformar a experiência do funcionário.** Manter os principais executores permitindo que os gerentes e funcionários conectem experiências de auto-atendimento que impulsionam o envolvimento e o crescimento.
- **Otimizar os programas de RH.** Ajudar a diminuir os custos operacionais e criar programas de licença e ausência, tempo, benefício e gerenciamento de remuneração centrados em pessoas.
- **Aumentar a agilidade organizacional.** Habilite o RH para operar com a destreza que os negócios exigem usando Dataverse e Microsoft Power Platform para centralizar os dados de pessoal e estender facilmente o Dynamics 365 Human Resources.
- **Descobrir as informações da força de trabalho.** Tome decisões controladas por dados com a capacidade de analisar e visualizar dados de pessoas em painéis avançados que estão disponíveis em qualquer dispositivo.

## <a name="human-resources-infrastructure-merge"></a>Mesclagem de infraestrutura de Human Resources

O Dynamics 365 Human Resources é um aplicativo autônomo que atualmente usa uma infraestrutura diferente de outros aplicativos de finanças e operações, como, Dynamics 365 Finance ou Dynamics 365 Supply Chain Management. A mesclagem de infraestrutura colocará o Dynamics 365 Human Resources na mesma infraestrutura de outros aplicativos de finanças e operações.

Para saber mais sobre a mesclagem de infraestrutura de Human Resources, consulte [Mesclagem de ofertas de HR](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers/). Para obter respostas para perguntas frequentes, consulte [Perguntas frequentes sobre a mesclagem de infraestrutura do Human Resources](./hr-infrastructure-merge-faq.md).

## <a name="customer-migration-vs-customer-merge"></a>Migração de clientes vs. mesclagem de clientes

Como parte da mesclagem da infraestrutura, todos os recursos do aplicativo Human Resources foram disponibilizados em ambientes financeiros e operacionais. Os clientes podem migrar seus ambientes de Human Resources usando as ferramentas de migração disponíveis nos Lifecycle Services do Microsoft Dynamics. Opcionalmente, eles também podem mesclar os dados com o ambiente financeiro e as operações existentes. 

A migração do cliente e a mesclagem de clientes diferem da seguinte maneira:

- **Migração de clientes** – a ferramenta de migração automatizada é usada para executar uma "migração lift-and-shift" (movimento) do banco de dados do cliente da infraestrutura do Human Resources para a infraestrutura de finanças e operações. O resultado é um novo ambiente de finanças e operações que usa o banco de dados do Human Resources do cliente. 
- **Mesclagem do cliente** – essa etapa adicional não é necessária para a Microsoft. Isso é feito a critério do cliente e na linha do tempo do próprio cliente. Durante esta etapa, os dados do cliente são movidos para um ambiente existente, como um ambiente do Finance ou do Project Operations. Ele é, na maioria das vezes, manual e pode ser feito usando entidades de dados DMF (Data Management Framework). 

## <a name="planning-a-human-resources-environment-migration"></a>Planejando uma migração de ambiente do Human Resources

Como parte da mesclagem de infraestrutura, será necessário que todos os clientes migrem os ambientes do Human Resources da infraestrutura autônoma. Para ajudar esse processo, recomendamos que você use a ferramenta de migração automatizada no Lifecycle Services para mover os ambientes atuais para a nova infraestrutura. 

As seções a seguir fornecem mais detalhes sobre como usar as ferramentas do Lifecycle Services para migrar um ambiente do Human Resources autônomo. 

Os clientes que estão planejando uma migração podem ter as seguintes expectativas:

- Todos os clientes deverão migrar um ambiente de área restrita, antes que o ambiente de produção possa ser migrado. 
- As ferramentas de migração permitem apenas migração de área restrita para área restrita e de produção para produção. Portanto, seu tipo de ambiente determinará que ambiente pode ser migrado apropriadamente. 
- Os clientes podem migrar quantas áreas restritas forem necessárias, antes de migrar seu ambiente de produção, desde que um slot de área restrita de destino esteja disponível. Os clientes também podem excluir uma área restrita migrada e migrá-las várias vezes. 
- Se uma migração de área restrita falhar ou se você quiser recomeçar, poderá excluir um ambiente na infraestrutura de finanças e operações e migrar o mesmo ambiente.
- A URL do seu ambiente do Human Resources será diferente após a migração.
- Planeje uma quantidade de tempo de inatividade adequada para a migração de seu ambiente de produção. O período previsto para a conclusão do processo de migração automatizada é de três a quatro horas. O período vai variar, dependendo dos dados da sua organização. Você deve validar o tempo necessário durante a migração de seus ambientes de área restrita e permite o tempo de qualquer tarefa manual adicional que deve ser concluída.

> [!IMPORTANT] 
> Quando um ambiente de produção é migrado com êxito para a infraestrutura de finanças e operações, o ambiente de produção autônomo de origem é excluído automaticamente. Você não deve excluir o ambiente de produção migrado. 

O processo para a migração é quase automático. No entanto, os usuários de negócios terão de concluir algumas etapas manuais e a validação após a migração.

As seguintes etapas manuais devem ser concluídas:

- Crie um novo projeto do Lifecycle Services para a migração.
- Revise todas as integrações do seu ambiente antigo para o novo ambiente apontando a integração para as novas URL/empresas, com base em cada configuração de integração.
- Atualize o armazenamento de dados para relatórios do Power BI inseridos.
- Atualize a lista de entidades de dados do espaço de trabalho DMF.
- Link para Lifecycle Services para ajuda.
- Criar calendários fiscais.

Durante o processo automático, as seguintes ações são concluídas e devem ser validadas:

- Dados:

    - Configurações
    - Funções de segurança (incluindo funções personalizadas)
    - Fluxos de trabalho
    - Personalizações e exibições salvas
    - Transações
    - Campos personalizados
    - Anexos

- Gerenciamento de dados – Trazer seu próprio banco de dados (BYOD).
- Gerenciamento de recursos - Recursos habilitados/desabilitados.
- Power Apps incorporado.
- Ambiente anexado do centro de administração do Power Platform (somente produção).
- Trabalhos em Lotes.
- Um razão vazio é criado para cada entidade legal. O tipo de taxa de câmbio padrão e a moeda contábil para cada razão são definidos.
- Um novo plano de contas é criado automaticamente e vinculado ao **Razão** em cada entidade legal. As dimensões financeiras configuradas no seu ambiente do Human Resources serão adicionadas automaticamente a uma nova estrutura de conta e vinculadas ao razão. 

> [!NOTE]
> Um razão é necessário na infraestrutura de finanças e operações como parte do produto Dynamics 365 Finance. O controlador de dimensão personalizado que existia no aplicativo autônomo do Dynamics 365 Human Resources não está disponível. A infraestrutura mesclada do Human Resources depende da lógica financeira para mostrar as dimensões financeiras no módulo **Human Resources**. Para saber mais sobre o plano de contas e as dimensões financeiras, consulte [aqui](../finance/general-ledger/plan-chart-of-accounts.md). 

## <a name="considerations"></a>Considerações

- A migração para ambientes sempre estará na versão mais recente disponível no mercado (GA). Dependendo da migração e do plano de testes, se a validação da migração para ambientes de área restrita estava em uma versão diferente, recomendamos que você valide uma migração de área restrita na mesma versão que seu ambiente de produção. 
- Durante a migração, os ambientes migrados serão colocados na mesma região que os ambientes autônomos de origem do Human Resources.

## <a name="licensing"></a>Licenciamento

Não há alterações no licenciamento do Dynamics 365 Human Resources nas seguintes áreas: 

- **Número mínimo de requisito de compra de licença**
- **Licenças para um ambiente de produção e um ambiente de área restrita** – se você tiver licenças autônomas do Human Resources que incluem um ambiente de produção e um ambiente de área restrita, o mesmo número de licenças estará disponível na infraestrutura de finanças e operações.
- **Licenças de área restrita adicionais** – se você comprou licenças de área restrita adicionais para o aplicativo autônomo do Human Resources, o mesmo número de licenças de área restrita estará disponível para ambientes de teste de aceitação padrão (área restrita) na infraestrutura de finanças e operações, sem custo adicional. 
