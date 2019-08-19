---
title: Adicionar local e tipos de relacionamento do participante
description: Este tópico explica como adicionar um novo local e tipo de relacionamento do participante.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8c359c5c33bed5b5abe7fc0c8e362c3399e9051a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836667"
---
# <a name="add-location-roles-and-party-relationship-types"></a>Adicionar funções de local e tipos de relacionamentos do participante 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a>Adicionar funções de localização

Há duas maneiras de adicionar novas funções do local para endereço e informações de contato:

-  Adicione-as através da página **Finalidade das informações de endereço e de contato**. A nova função será salva na tabela **LogisticsLocationRole** com tipo = 0, que indica que a função não é definida pelo sistema na enumeração **LogisticsLocationRoleType** e em suas extensões. Um usuário poderá usar esta função ao criar o endereço ou informações de contato.

    ![Finalidade das informações de endereço e de conteúdo](media/Address-Contact.PNG)

-  Adicione-a à extensão de enumeração **LogisticsLocationRoleType** e deixe-a preencher através do processo de sincronização do banco de dados.

    1.  Crie uma extensão para a enumeração **LogisticsLocationRoleType** e adicione a nova função na extensão. 
  
        ![LogisticsLocationRoleType](media/Logistics.PNG)

    2. Crie um novo arquivo de recursos para a nova função, e atribua um valor para suas propriedades.
     
     ![Novo arquivo de recurso](media/Resource.PNG)
        
    3.  Crie uma classe da população de dados e forneça um método do manipulador para preencher a nova função. 

        ![Preenchimento de dados](media/Dirdata.PNG)

    4.  Para testar o preenchimento da nova função do local, você pode criar uma classe executável e chamar DirDataPopulation::insertLogisticsLocationRoles() in Main(). Depois que esse processo for concluído, você deverá ver a nova função preenchida na tabela **LogisticsLocationRole** com tipo \> 0. A nova função será exibida na página **Finalidade das informações de endereço e de contato**.

        ![Inserir novo local](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a>Adicionar tipos de relacionamento do participante 

Há duas maneiras de adicionar um novo tipo de relacionamento:

-   Adicione-o através da página **Tipos de relacionamento**. O novo relacionamento será salvo na **DirRelationshipTypeTable** com systemtype = 0.

    ![Tipos de relacionamentos](media/Relationship.PNG)

-  Adicione-o à extensão da enumeração **DirSystemRelationshipType** e deixe-o preencher através do processo de sincronização do banco de dados.

    1.  Crie uma extensão para a enumeração **DirSystemRelationshipType** e adicione o novo tipo de relacionamento.

    2. Crie um inicializador para este novo tipo. Você pode encontrar vários exemplos no código principal, um deles é **DirRelationshipTypeChildInitialize**. Esta é uma classe do inicializador para o tipo de relacionamento da parte "Filho". Comece com o inicializador, copiando e colando este código e, em seguida, atualize as áreas destacadas.
    
    ![DirRelationshipChild](media/DirRelationship.PNG)

    3.  Para testar o preenchimento do novo tipo de relacionamento você pode criar uma classe executável e chamar DirDataPopulation::insertDirRelationshipTypes() in Main(). Você deve verificar o novo tipo de relacionamento na **DirRelationshipTypeTable** e o novo tipo de relacionamento estará disponível na página **Tipos de relacionamento** .

        ![Classe executável](media/Runnable.PNG)
