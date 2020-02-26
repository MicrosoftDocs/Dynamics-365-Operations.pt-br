---
title: Remover uma instância
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5c5f875ad9361c31af4fbe863488b881cdd97a6e
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008043"
---
# <a name="remove-an-instance"></a>Remover uma instância

Este artigo mostra o processo de remoção de um ambiente de produção ou de test drive do Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Remover um ambiente de test drive

Os test drives do Human Resources são provisionados com uma política de vencimento de 60 dias. No entanto, os proprietários de ambientes de test drive têm a opção de encerrar sua avaliação antecipadamente concluindo as seguintes etapas. 

1. Navegue até o [Centro de administração do Power Apps](https://admin.businessplatform.microsoft.com/).
2. Selecione **Ambientes**.
3. Selecione o ambiente de test drive, que possui um padrão de nomenclatura semelhante a este: TestDrive - alias@domain
4. Selecione **Excluir** e confirme a decisão. 

O ambiente de test drive existente será removido. Quando for removido, inscreva-se em um novo ambiente de test drive. 

## <a name="remove-a-production-environment"></a>Remover um ambiente de produção

Este tópico pressupõe que você adquiriu o Human Resources por meio de um Provedor de Soluções na Nuvem (CSP) ou de um contrato de arquitetura da empresa (EA). 

Como um ambiente único do Human Resources é contido em um ambiente único do Power Apps, há duas opções a serem consideradas. A primeira opção envolve a remoção de todo o ambiente do Power Apps; a segunda opção envolve somente a remoção do Human Resources. A primeira opção é preferível quando você tiver criado um ambiente do Power Apps especificamente para provisionar o Human Resources e tiver acabado de iniciar a implementação, ou se não tiver nenhuma integração estabelecida. A segunda opção será recomendável quando você tiver um ambiente estabelecido do Power Apps preenchido com dados avançados aproveitados no Power Apps e no Power Automate.

> [!Important]
> Antes de remover o ambiente do Power Apps, verifique se ele não está sendo usado para integrações de dados avançados fora do escopo do Human Resources. Observe também que os ambientes do Power Apps não podem ser removidos. 

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
4.  Entre no LCS usando a conta utilizada para inscrever-se no Human Resources. 
5. Selecione o projeto do Human Resources que contém o ambiente. 
6. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**. 
7. Selecione a instância que você deseja remover, que deve estar marcada com um status de implantação **Reprovado**.
8. Selecione **Remover instância** e confirme sua decisão. 
