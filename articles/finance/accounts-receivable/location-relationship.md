---
title: Adicionar local e tipos de relacionamento do participante
description: Este artigo explica como adicionar um novo local e tipo de relacionamento do participante.
author: ShivamPandey-msft
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2aaf16fac658d26dc2d2a389fd5c1dbb9cbb7649
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874744"
---
# <a name="add-location-and-party-relationship-types"></a>Adicionar local e tipos de relacionamento do participante 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a>Adicionar funções de localização

Há duas maneiras de adicionar novas funções do local para endereço e informações de contato:

-  Adicione-as através da página **Finalidade das informações de endereço e de contato**. A nova função será salva na tabela **LogisticsLocationRole** com tipo = 0, que indica que a função não é definida pelo sistema na enumeração **LogisticsLocationRoleType** e em suas extensões. Um usuário poderá usar esta função ao criar o endereço ou informações de contato.

    ![Finalidade das informações de endereço e de conteúdo.](media/Address-Contact.PNG)

-  Adicione-a à extensão de enumeração **LogisticsLocationRoleType** e deixe-a preencher através do processo de sincronização do banco de dados.

    1.  Crie uma extensão para a enumeração **LogisticsLocationRoleType** e adicione a nova função na extensão. 
  
        ![Extensão para a enumeração LogisticsLocationRoleType.](media/Logistics.PNG)

    2. Crie um novo arquivo de recursos para a nova função, e atribua um valor para suas propriedades.
     
     ![Novo arquivo de recurso.](media/Resource.PNG)
        
    3.  Crie uma classe da população de dados e forneça um método do manipulador para preencher a nova função. 

        ![Preenchimento de dados.](media/Dirdata.PNG)

    4.  Para testar o preenchimento da nova função do local, você pode criar uma classe executável e chamar DirDataPopulation::insertLogisticsLocationRoles() in Main(). Depois que esse processo for concluído, você deverá ver a nova função preenchida na tabela **LogisticsLocationRole** com tipo \> 0. A nova função será exibida na página **Finalidade das informações de endereço e de contato**.

        ![Inserir novo local.](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a>Adicionar tipos de relacionamento do participante 

Há duas maneiras de adicionar um novo tipo de relacionamento:

-   Adicione-o através da página **Tipos de relacionamento**. O novo relacionamento será salvo na **DirRelationshipTypeTable** com systemtype = 0.

    ![Tipos de relacionamentos.](media/Relationship.PNG)

-  Adicione-o à extensão da enumeração **DirSystemRelationshipType** e deixe-o preencher através do processo de sincronização do banco de dados.

    1.  Crie uma extensão para a enumeração **DirSystemRelationshipType** e adicione o novo tipo de relacionamento.

    2. Crie um inicializador para este novo tipo. Você pode encontrar vários exemplos no código principal, um deles é **DirRelationshipTypeChildInitialize**. Esta é uma classe do inicializador para o tipo de relacionamento da parte "Filho". Comece com o inicializador, copiando e colando este código e, em seguida, atualize as áreas destacadas.
    
    ![Inicializador de DirRelationshipChild.](media/DirRelationship.PNG)

    3.  Para testar o preenchimento do novo tipo de relacionamento você pode criar uma classe executável e chamar DirDataPopulation::insertDirRelationshipTypes() in Main(). Você deve verificar o novo tipo de relacionamento na **DirRelationshipTypeTable** e o novo tipo de relacionamento estará disponível na página **Tipos de relacionamento** .

        ![Classe executável.](media/Runnable.PNG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
