---
title: Mesclagem de infraestrutura do Dynamics 365 Human Resources – atualização da versão 10.0.25
description: Este tópico fornece informações sobre o Microsoft Dynamics 365 Human Resources versão 10.0.25, que traz o primeiro ciclo de recursos na mesclagem de infraestrutura.
author: twheeloc
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a80bedd0224f1e31dfec4e9f4c39ad1ed75d7f2f
ms.sourcegitcommit: 948978183a1da949e35585b28b8e85a63b6c12b1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2022
ms.locfileid: "8024558"
---
# <a name="dynamics-365-human-resources-infrastructure-merge---release-10025-update"></a>Mesclagem de infraestrutura do Dynamics 365 Human Resources – atualização da versão 10.0.25

A versão 10.0.25 traz o primeiro ciclo de recursos da mesclagem de infraestrutura. Durante a mesclagem de infraestrutura, o Microsoft Dynamics 365 Human Resources será mesclado com a infraestrutura do Finance and Operations. No entanto, ele continuará a ser licenciado como um aplicativo independente, como o Dynamics 365 Finance e o Dynamics 365 Supply Chain Management. Para obter mais informações sobre a mesclagem de infraestrutura, consulte [Perguntas frequentes sobre a mesclagem de infraestrutura do Dynamics 365 Human Resources](../human-resources/hr-infrastructure-merge-faq.md).

A mesclagem fornecerá consistência para os usuários do Human Resources das seguintes maneiras:

- [O gerenciamento e as integrações de ambiente são consistentes entre os aplicativos do Human Resources e Finance and Operations.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/consistent-environment-management-integrations-between-human-resources-finance-operations-apps)

    - Gerenciar ambientes no Microsoft Dynamics Lifecycle Services, na pesquisa de problemas e na Regression Suite Automation Tool.
    - Há um único código base, no qual novas funcionalidades para o Human Resources são lançadas como parte do processo de atualização One Version.
    - A forma como os upgrades, as atualizações e os hotfixes são aplicados aos ambientes é consistente.

- [As opções de extensibilidade foram aprimoradas.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/improve-extensibility-options.md)

    - Você pode continuar a usar as ferramentas do Microsoft Power Platform para estender conforme necessário.
    - Você pode estender a funcionalidade por meio de formulários, tabelas, métodos e APIs (interfaces de programação de aplicativo).
    - Você pode criar e estender entidades.

    Para obter mais informações sobre as opções de extensão disponíveis, consulte [Visão geral da extensibilidade no Dynamics 365](../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md).

- [Criar um conjunto de recursos de recursos humanos no Dynamics 365.](/dynamics365-release-plan/2021wave2/human-resources/create-one-set-human-resources-capabilities-within-dynamics-365.md)

    Na versão 10.0.25, os recursos funcionais que existiam somente no Human Resources foram disponibilizados na infraestrutura do Finance and Operations. Para que os clientes aproveitem esses recursos em um ambiente do Finance and Operations, os seguintes recursos do Human Resources devem estar habilitados no Gerenciamento de Recursos.

    | Nome do recurso | Visão Geral | Status da liberação | 
    |--------------|----------|----------------| 
    | Cálculo de anos de serviço | Uma opção de configuração permite selecionar a data usada para o cálculo de **Anos de serviço**. | Geralmente disponível | 
    | Aprimoramentos na experiência de fluxo de trabalho | Esse recurso oferece uma experiência de usuário aprimorada para envios e aprovações do fluxo de trabalho. | Geralmente disponível | 
    | Imprimir revisões de desempenho | Você pode imprimir avaliações de desempenho em formato PDF. | Geralmente disponível | 
    | Links personalizados em **Autoatendimento para gerentes** | Você pode criar links personalizados que aparecem na seção **Links relacionados** de **Autoatendimento para gerentes**. | Geralmente disponível | 
    | Exibição da remuneração interempresarial | Os usuários podem exibir planos de compensação em **Autoatendimento para gerentes** em todas as entidades legais, sem a necessidade de troca de empresas. | Geralmente disponível | 
    | Configurar vários níveis de compensação por trabalho\*&dagger; | Agora, os trabalhos dão suporte a vários níveis de compensação. | Versão preliminar | 
    | Gerenciamento de Tarefas\* | Você pode criar listas de verificação e tarefas para o processo de integração, remoção e transição. | Versão preliminar | 
    | Entrada de funcionário simplificada | Esse recurso oferece uma experiência de usuário atualizada na página **Trabalhador** existente. | Versão preliminar | 
    | Aprimoramentos na experiência do usuário de recursos humanos | Consulte a tabela na próxima seção.  | Versão preliminar | 

\* Esse recurso deve ser ativado antes do recurso **Aprimoramentos na experiência do usuário de recursos humanos**.

&dagger; Esse recurso não poderá ser desabilitado depois de habilitado.

## <a name="human-resource-user-experience-enhancements"></a>Aprimoramentos na experiência do usuário de recursos humanos

| Nome do recurso | Visão Geral | 
|--------------|----------| 
| Excluir emprego | Você pode excluir um emprego de um funcionário. | 
| Famílias de trabalho | Você pode acompanhar um grupo de trabalhos que envolva trabalho semelhante e que exija treinamento, habilidades, conhecimento e experiência semelhantes. | 
| Campos de emprego adicionais | Os campos a seguir foram adicionados: **Categoria de emprego**, **Tipo de emprego** e **Status de emprego**. | 
| Página **Trabalhadores sem emprego** | Uma página mostra uma lista de trabalhadores que não têm um registro de emprego. | 
| Atualização da experiência do usuário da dimensão de posição | Há uma experiência de usuário aprimorada para atribuir dimensões de posição por entidade legal. | 
| Alterações de endereço no espaço de trabalho **Gerenciamento de pessoal** | Esse recurso fornece uma contagem de todas as alterações de endereço que ocorreram durante um número de dias específico, conforme definido na página **Parâmetros de recursos humanos**. | 
| Registros em vencimento no espaço de trabalho **Gerenciamento de pessoal** | Esse recurso fornece uma lista de itens vencidos ou que vencerão para certificados, identificações, períodos de experiência, triagens ou testes. | 
| Página **Validação de hierarquia de posição** | Uma verificação é feita para referências circulares na hierarquia de linhas de posição. | 
| Informações específicas da folha de pagamento do país/região | Os campos de folha de pagamento adicionais estão disponíveis na página **Emprego do trabalhador**, dependendo do país ou região da entidade legal na qual os trabalhadores estão empregados. | 
| Aprimoramentos no relatório de conformidade | As opções de relatório adicionais estão disponíveis para EEO-1, Vets 4212 e OSHA300a. | 
| Atualizações no espaço de trabalho **Gerenciamento de pessoal** | Foram feitas atualizações para acompanhar alterações de endereço e registros em vencimento. Além disso, novas guias listam ações de trabalhador e posição. | 
