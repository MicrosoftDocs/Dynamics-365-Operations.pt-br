---
title: Adicionar local e tipos de relacionamento do participante
description: "Este tópico explica como adicionar um novo local e tipo de relacionamento do participante."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bf971bc6cf4b11de6381e369235d582678d074fc
ms.openlocfilehash: 8de914e0fb853cdc9aa36e55a02156757793abc3
ms.contentlocale: pt-br
ms.lasthandoff: 06/12/2018

---

# <a name="add-new-location-roles-and-party-relationship-types"></a><span data-ttu-id="b134a-103">Adicionar novas funções de local e tipos de relacionamentos do participante.</span><span class="sxs-lookup"><span data-stu-id="b134a-103">Add new location roles and party relationship types</span></span> 

## <a name="add-new-location-roles"></a><span data-ttu-id="b134a-104">Adicionar novas funções do local</span><span class="sxs-lookup"><span data-stu-id="b134a-104">Add new location roles</span></span>

<span data-ttu-id="b134a-105">Há duas maneiras de adicionar novas funções do local para endereço e informações de contato:</span><span class="sxs-lookup"><span data-stu-id="b134a-105">There are two ways to add a new location roles for address and contact information:</span></span>

-  <span data-ttu-id="b134a-106">Adicione-as através da página **Finalidade das informações de endereço e de contato**.</span><span class="sxs-lookup"><span data-stu-id="b134a-106">Add it through the **Address and contact information purpose** page.</span></span> <span data-ttu-id="b134a-107">A nova função será salva na tabela **LogisticsLocationRole** com tipo = 0, que indica que a função não é definida pelo sistema na enumeração **LogisticsLocationRoleType** e em suas extensões.</span><span class="sxs-lookup"><span data-stu-id="b134a-107">The new role will be saved to the **LogisticsLocationRole** table with type = 0, which indicates that the role is not a system role defined in the **LogisticsLocationRoleType** enum and its extensions.</span></span> <span data-ttu-id="b134a-108">Um usuário poderá usar esta função ao criar o endereço ou informações de contato.</span><span class="sxs-lookup"><span data-stu-id="b134a-108">A user will be able to use this role when creating address or contact information.</span></span>

    ![Finalidade das informações de endereço e de conteúdo](media/Address-Contact.PNG)

-  <span data-ttu-id="b134a-110">Adicione-a à extensão de enumeração **LogisticsLocationRoleType** e deixe-a preencher através do processo de sincronização do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b134a-110">Add it to the **LogisticsLocationRoleType** enum extension, and let it populate through the database sync process.</span></span>

    1.  <span data-ttu-id="b134a-111">Crie uma extensão para a enumeração **LogisticsLocationRoleType** e adicione a nova função na extensão.</span><span class="sxs-lookup"><span data-stu-id="b134a-111">Create an extension to the **LogisticsLocationRoleType** enum and add the new role in the extension.</span></span> 
  
        ![LogisticsLocationRoleType](media/Logistics.PNG)

    2. <span data-ttu-id="b134a-113">Crie um novo arquivo de recursos para a nova função, e atribua um valor para suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="b134a-113">Create a new resource file for the new role, and then assign a value for its properties.</span></span>
     
     ![Novo arquivo de recurso](media/Resource.PNG)
        
    3.  <span data-ttu-id="b134a-115">Crie uma classe da população de dados e forneça um método do manipulador para preencher a nova função.</span><span class="sxs-lookup"><span data-stu-id="b134a-115">Create a data population class and provide a handler method to populate the new role.</span></span> 

        ![Preenchimento de dados](media/Dirdata.PNG)

    4.  <span data-ttu-id="b134a-117">Para testar o preenchimento da nova função do local, você pode criar uma classe executável e chamar DirDataPopulation::insertLogisticsLocationRoles() em Main().</span><span class="sxs-lookup"><span data-stu-id="b134a-117">To test populating the new location role, you can create a runnable class, and call DirDataPopulation::insertLogisticsLocationRoles() in Main().</span></span> <span data-ttu-id="b134a-118">Depois que esse processo for concluído, você deverá ver a nova função preenchida na tabela **LogisticsLocationRole** com tipo \> 0.</span><span class="sxs-lookup"><span data-stu-id="b134a-118">After this process is complete, you should see the new role populated in the **LogisticsLocationRole** table with type \> 0.</span></span> <span data-ttu-id="b134a-119">A nova função será exibida na página **Finalidade das informações de endereço e de contato**.</span><span class="sxs-lookup"><span data-stu-id="b134a-119">The new role will display on the **Address and contact information purpose** page.</span></span>

        ![Inserir novo local](media/InsertNewLocation.PNG)

## <a name="add-new-party-relationship-types"></a><span data-ttu-id="b134a-121">Adicionar novos tipos de relacionamento do participante</span><span class="sxs-lookup"><span data-stu-id="b134a-121">Add new party relationship types</span></span> 

<span data-ttu-id="b134a-122">Há duas maneiras de adicionar um novo tipo de relacionamento:</span><span class="sxs-lookup"><span data-stu-id="b134a-122">There are two ways to add a new relationship type:</span></span>

-   <span data-ttu-id="b134a-123">Adicione-o através da página **Tipos de relacionamento**.</span><span class="sxs-lookup"><span data-stu-id="b134a-123">Add it through the **Relationship types** page.</span></span> <span data-ttu-id="b134a-124">O novo relacionamento será salvo na **DirRelationshipTypeTable** com systemtype = 0.</span><span class="sxs-lookup"><span data-stu-id="b134a-124">The new relationship will be saved to **DirRelationshipTypeTable** with systemtype = 0.</span></span>

    ![Tipos de relacionamentos](media/Relationship.PNG)

-  <span data-ttu-id="b134a-126">Adicione-o à extensão da enumeração **DirSystemRelationshipType** e deixe-o preencher através do processo de sincronização do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b134a-126">Add it to the extension of the **DirSystemRelationshipType** enum, and let it populate through database sync process.</span></span>

    1.  <span data-ttu-id="b134a-127">Crie uma extensão para a enumeração **DirSystemRelationshipType** e adicione o novo tipo de relacionamento.</span><span class="sxs-lookup"><span data-stu-id="b134a-127">Create an extension to the **DirSystemRelationshipType** enum and add the new relationship type.</span></span>

    2. <span data-ttu-id="b134a-128">Crie um inicializador para este novo tipo.</span><span class="sxs-lookup"><span data-stu-id="b134a-128">Create an initializer for this new type.</span></span> <span data-ttu-id="b134a-129">Você pode encontrar vários exemplos no código principal, um deles é **DirRelationshipTypeChildInitialize**.</span><span class="sxs-lookup"><span data-stu-id="b134a-129">You can find several examples in the core code, one of them is  **DirRelationshipTypeChildInitialize**.</span></span> <span data-ttu-id="b134a-130">Esta é uma classe do inicializador para o tipo de relacionamento da parte "Filho".</span><span class="sxs-lookup"><span data-stu-id="b134a-130">This is an initializer class for party relationship type “Child”.</span></span> <span data-ttu-id="b134a-131">Comece com o inicializador, copiando e colando este código e, em seguida, atualize as áreas destacadas.</span><span class="sxs-lookup"><span data-stu-id="b134a-131">You can start with your initializer by copying and pasting this code and then update the highlighted areas.</span></span>
    
    ![DirRelationshipChild](media/DirRelationship.PNG)

    3.  <span data-ttu-id="b134a-133">Para testar o preenchimento do novo tipo de relacionamento você pode criar uma classe executável e chamar DirDataPopulation::insertDirRelationshipTypes() em Main().</span><span class="sxs-lookup"><span data-stu-id="b134a-133">To test populating the new relationship type, you can create a runnable class, and call DirDataPopulation::insertDirRelationshipTypes() in Main().</span></span> <span data-ttu-id="b134a-134">Você deve verificar o novo tipo de relacionamento na **DirRelationshipTypeTable** e o novo tipo de relacionamento estará disponível na página **Tipos de relacionamento** .</span><span class="sxs-lookup"><span data-stu-id="b134a-134">You should see the new relationship type in the **DirRelationshipTypeTable**, and the new relationship type will be available on the **Relationship types** page.</span></span>

        ![Classe executável](media/Runnable.PNG)

