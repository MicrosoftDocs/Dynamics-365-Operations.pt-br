---
title: Criar canal online e definir atributos do canal
description: Este procedimento orienta na criação de um novo canal online e sua adição à hierarquia da organização.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f85a74e44be28452f5d892f1875d74261f9dbe3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215427"
---
# <a name="create-online-channel-and-define-channel-attributes"></a>Criar canal online e definir atributos do canal

[!include [banner](../includes/banner.md)]

Este procedimento orienta na criação de um novo canal online e sua adição à hierarquia da organização. É necessário criar a hierarquia da organização antes que você possa criar um novo canal online. Este procedimento usa a empresa de dados de demonstração USRT.


## <a name="create-a-new-online-channel"></a>Criar um novo canal online
1. Vá para Varejo e Comércio > Canais > Lojas online.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Depósito, insira ou selecione um valor.
5. No campo Fuso horário da loja, selecione uma opção.
6. No campo Cliente padrão, insira ou selecione um valor.
7. No campo Catálogo de endereços do cliente, insira ou selecione um valor.
8. No campo Condições de pagamento, insira ou selecione um valor.
9. No campo Condições de pagamento, insira ou selecione um valor.
10. No campo Notificação por email, insira ou selecione um valor.
11. Expanda a seção Dimensões financeiras.
12. No campo Unidade de negócios, insira ou selecione um valor.
    * De modo semelhante, defina o valor para todas as outras dimensões padrão.  
13. Clique em Salvar.

## <a name="add-the-online-channel-to-organization-hierarchy"></a>Adicionar o canal online à hierarquia da organização
1. Feche a página.
2. Vá para Administração da organização > Organizações > Hierarquias da organização.
3. Na lista, localize e selecione o PDV desejado.
4. Clique em Exibir.
5. Clique em Editar.
    * Você pode selecionar qualquer nó da hierarquia no qual deseja inserir o novo canal.  
6. Clique em Inserir.
7. Clique em Canal de comércio.
8. Clique em OK.
9. Clique em Publicar para abrir a caixa de diálogo suspensa.
10. No campo de data efetiva, insira uma data e hora.
11. Clique em Publicar.

## <a name="configure-orders-for-near-real-time-notification"></a>Configurar ordens para notificação quase em tempo real
1. Vá para Varejo e Comércio > Configuração da sede > Parâmetros > Parâmetros de comércio.
2. Definir Usar serviço em tempo real para criação de ordens de comércio eletrônico como "Sim".
3. Execute a agenda de distribuição 1070 para sincronizar alterações no banco de dados do canal. 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]