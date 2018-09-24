---
title: Remover ambientes do Talent
description: "Este tópico mostra o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: 5080f1ec182b8cbdf281967185a1afeb9887f682
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="remove-talent-environments"></a>Remover ambientes do Talent

[!include [banner](includes/banner.md)]

Este tópico mostra o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 for Talent.

## <a name="removing-a-test-drive-environment"></a>Removendo um ambiente de test drive

Os test drives do Talent são provisionados com uma política de vencimento de 60 dias. No entanto, os proprietários de ambientes de test drive têm a opção de encerrar sua avaliação antecipadamente concluindo as seguintes etapas. 

1. Navegue até o [Centro de Administração do PowerApps](https://admin.businessplatform.microsoft.com/).
2. Selecione **Ambientes**.
3. Selecione o ambiente de test drive, que possui um padrão de nomenclatura semelhante a este: TestDrive - alias@domain
4. Selecione **Excluir** e confirme a decisão. 

O ambiente de test drive existente será removido. Quando for removido, inscreva-se em um novo ambiente de test drive. 

## <a name="removing-a-production-environment"></a>Removendo um ambiente de produção

Este tópico pressupõe que você adquiriu o Talent por meio de um Provedor de Soluções na Nuvem (CSP) ou de um contrato de arquitetura da empresa (EA). 

Como um ambiente único do Talent é “contido" em um ambiente único do PowerApps, há duas opções a serem consideradas. A primeira opção envolve a remoção de todo o ambiente do PowerApps; a segunda opção envolve somente a remoção do Talent. A primeira opção é preferível quando você tiver criado um ambiente do PowerApps especificamente para provisionar o Talent e tiver acabado de iniciar a implementação, ou se não tiver nenhuma integração estabelecida. A segunda opção é recomendável quando você tiver um ambiente estabelecido do PowerApps preenchido com dados sofisticados aproveitados no PowerApps e nos fluxos.

> [!Important]
> Antes de remover o ambiente do PowerApps, verifique se ele não está sendo usado para integrações de dados sofisticados fora do escopo do Talent. Observe também que os ambientes do PowerApps não podem ser removidos. 

Para remover todo o ambiente do PowerApps, incluindo o Talent e os aplicativos e fluxos associados:

1. Navegue até o [Centro de Administração do PowerApps](https://admin.businessplatform.microsoft.com/).
2. Selecione **Ambientes**.
3. Selecione o ambiente a ser removido.
4. Selecione **Excluir** e confirme a decisão. 
5. Aguarde até que a exclusão seja concluída.
6. Entre no [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) usando a conta utilizada para inscrever-se no Talent. 
7. Selecione o projeto do Talent que contém o ambiente. 
8. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo Talent**. 
9. Selecione a instância a ser removida. 
10. Selecione **Remover instância** e confirme sua decisão.  

Para remover um ambiente do Talent de um ambiente existente do PowerApps, conclua estas etapas. Observe que a necessidade de envolver o suporte e contatar a equipe do Talent DevOps é temporária até que esse recurso seja habilitado diretamente no LCS.

1. Contate o suporte para iniciar uma solicitação de remoção.
2. A equipe de suporte iniciará uma solicitação de remoção com a equipe do Talent DevOps. 
3. Continue após ser informado de que o ambiente foi removido.
4.  Entre no LCS usando a conta utilizada para inscrever-se no Talent. 
5. Selecione o projeto do Talent que contém o ambiente. 
6. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo Talent**. 
7. Selecione a instância que você deseja remover, que deve estar marcada com um status de implantação **Reprovado**.
8. Selecione **Remover instância** e confirme sua decisão. 


