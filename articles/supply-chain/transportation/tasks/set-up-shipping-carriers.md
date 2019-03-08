---
title: Configurar transportadoras
description: Este procedimento descreve como montar uma transportadora e definir detalhes como serviço, modo de envio, proposta de transporte, restrições de transporte e taxa de envio.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c5ac13d17c97f20ee79e7faf57c570f02158424
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "314477"
---
# <a name="set-up-shipping-carriers"></a>Configurar transportadoras

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento descreve como montar uma transportadora e definir detalhes como serviço, modo de envio, proposta de transporte, restrições de transporte e taxa de envio. Um coordenador de transporte pode então atribuir uma transportadora a uma carga de entrada ou de saída.


## <a name="create-a-new-shipping-carrier"></a>Crie uma nova transportadora
1. Vá para Gerenciamento de transporte > Configuração > Transportadoras > Transportadoras de envio.
2. Clique em Novo.
3. No campo Transportadora, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Modo, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o PDV desejado.
7. Na lista, clique no link na linha selecionada.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Preencha as informações gerais da transportadora
1. Ative a expansão da seção Visão geral.
2. Marque ou desmarque a caixa de seleção Ativar a transportadora.
3. No campo Fornecedor, clique no botão suspenso para abrir a pesquisa.
    * Selecione a conta do fornecedor para atribuí-la a transportadora.  
4. Na lista, localize e selecione o PDV desejado.
5. Na lista, clique no link na linha selecionada.
6. No campo Tipo de proposta de transporte, selecione uma opção.
    * Selecione Manual para usar a página Proposta de Transporte, ou selecione EDI para atualizar a proposta usando Intercâmbio Eletrônico de Dados (EDI).  
7. Marque ou desmarque a caixa de seleção Ativar a transportadora.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Crie os serviços necessários para a transportadora
1. Ative a expansão da seção Serviços.
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Serviço da transportadora, digite um valor.
5. No campo Nome, digite um valor.
6. No campo Método de transporte, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o PDV desejado.
8. Na lista, clique no link na linha selecionada.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Configure o endereço da transportadora (opcional)
1. Alternar a expansão da seção Endereços.
2. Clique em Novo.
3. No campo Nome ou Descrição, digite um valor.
4. No campo País/região, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
6. No campo CEP/código postal, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o registro desejado.
8. Na lista, clique no link na linha selecionada.
9. No campo Rua, digite um valor.
10. Clique em OK.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Configure o perfil de classificação para a transportadora.
1. Ative a expansão da seção Perfis de classificação.
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Perfil de classificação, digite um valor.
5. No campo Nome, digite um valor.
6. No campo Local, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o registro desejado.
8. Na lista, clique no link na linha selecionada.
9. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
10. Na lista, localize e selecione o registro desejado.
11. Na lista, clique no link na linha selecionada.
12. No campo Mecanismo de classificação, clique no botão suspenso para abrir a pesquisa.
    * Selecione o Mecanismo de taxa que está de acordo com o contrato que você tem com a transportadora.  
13. Na lista, localize e selecione o PDV desejado.
14. Na lista, clique no link na linha selecionada.
15. No campo Mestre de taxa, clique no botão suspenso para abrir a pesquisa.
16. Na lista, localize e selecione o registro desejado.
17. Na lista, clique no link na linha selecionada.
18. No campo Mecanismo de tempo de trânsito, clique no botão suspenso para abrir a pesquisa.
19. Na lista, clique no link na linha selecionada.
20. Clique em Salvar.

