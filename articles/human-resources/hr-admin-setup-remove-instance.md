---
title: Remover uma instância
description: Este artigo descreve o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ce676c93e133cc04ad9c49417ed2ca0d6791e93
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178460"
---
# <a name="remove-an-instance"></a>Remover uma instância

_**Aplica-se a:** Human Resources na infraestrutura autônoma_ 

> [!NOTE]
> A partir de 2022 de julho, novos ambientes do Human Resources não podem ser provisionados na infraestrutura autônoma do Human Resources, e novos projetos do Lifecycle Services (LCS) do Microsoft Dynamics não podem ser criados nele. Os clientes podem implantar ambientes de Recursos Humanos na infraestrutura de aplicativos de finanças e operações. Para obter mais informações, consulte [Provisionar Recursos Humanos na infraestrutura de finanças e operações](/hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> A infraestrutura de aplicativos de finanças e operações oferece suporte à exclusão de um ambiente. Para obter informações sobre como excluir um ambiente, consulte [Excluir um ambiente](../fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure.md#delete-an-environment).

Este artigo explica o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Remover um ambiente de test drive

Os test drives do Human Resources são provisionados com uma política de vencimento de 60 dias. No entanto, os proprietários de ambientes de test drive têm a opção de encerrar sua avaliação antecipadamente concluindo as seguintes etapas. 

1. Navegue até o [Centro de administração do Power Apps](https://admin.businessplatform.microsoft.com/).
2. Selecione **Ambientes**.
3. Selecione o ambiente de test drive, que possui um padrão de nomenclatura semelhante a este: TestDrive - alias@domain
4. Selecione **Excluir** e confirme a decisão. 

O ambiente de test drive existente será removido. Quando for removido, inscreva-se em um novo ambiente de test drive. 

## <a name="remove-a-production-environment"></a>Remover um ambiente de produção

Este tópico pressupõe que você adquiriu o Human Resources por meio de um Provedor de Soluções na Nuvem (CSP) ou de um contrato de arquitetura da empresa (EA). 

Como um ambiente único do Human Resources é contido em um ambiente único do Power Apps, há duas opções a serem consideradas ao remover um ambiente: 
- **Remover todo o ambiente do Power Apps.** Esta opção é preferencial quando o ambiente do Power Apps tiver sido criado com o objetivo de provisionar o Human Resources e tiver acabado de iniciar a implementação, ou se não tiver nenhuma integração estabelecida.  
- **Remover somente Human Resources.** Esta opção é apropriada quando houver um ambiente estabelecido do Power Apps preenchido com dados usados no Microsoft Power Apps e no Power Automate.


> [!Important]
> Antes de remover o ambiente do Power Apps, verifique se ele não está sendo usado para integrações de dados fora do escopo do Human Resources. Observe também que os ambientes do Power Apps não podem ser removidos. 

Para remover todo o ambiente do Power Apps, incluindo o Human Resources e os aplicativos e fluxos associados:

1. Navegue até o [Centro de administração do Power Apps](https://admin.businessplatform.microsoft.com/).
2. Selecione **Ambientes**.
3. Selecione o ambiente a ser removido.
4. Selecione **Excluir** e confirme a decisão. 
5. Aguarde até que a exclusão seja concluída.
6. Entre no [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) usando a conta utilizada para inscrever-se no Human Resources. 
7. Selecione o projeto do Human Resources que contém o ambiente. 
8. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**. 
9. Selecione a instância a ser removida. 
10. Selecione **Remover instância** e confirme sua decisão.  

Para remover um ambiente do Human Resources de um ambiente existente do Power Apps, conclua estas etapas. Observe que a necessidade de envolver o suporte e contatar a equipe do Human Resources DevOps é temporária até que esse recurso seja habilitado diretamente no LCS.

1. Contate o suporte para iniciar uma solicitação de remoção.
2. A equipe de suporte iniciará uma solicitação de remoção com a equipe do Human Resources DevOps. 
3. Continue após ser informado de que o ambiente foi removido.
4. Entre no LCS usando a conta utilizada para inscrever-se no Human Resources. 
5. Selecione o projeto do Human Resources que contém o ambiente. 
6. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**. 
7. Selecione a instância que você deseja remover, que deve estar marcada com um status de implantação **Excluído**.
8. Selecione **Remover instância** e confirme sua decisão. 

## <a name="recover-a-soft-deleted-environment"></a>Recuperar um ambiente excluído de forma reversível

Se você excluir o ambiente do Power Apps ao qual o seu ambiente do Human Resources está conectado, o status do ambiente do Human Resources no LCS será **Excluído de forma temporária**. Nesse caso, os usuários não podem se conectar aos Recursos Humanos.

Para restaurar o ambiente:

1. Siga as instruções no [ambiente Recuperar o Power Apps](/power-platform/admin/recover-environment).

2. Entre em contato com o suporte para restaurar o ambiente de Recursos Humanos. Para obter mais informações, consulte [Obter suporte](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

> [!Warning]
> Os ambientes do Power Apps só são salvos por sete dias após a exclusão. Você deve recuperar o ambiente no período de sete dias.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
