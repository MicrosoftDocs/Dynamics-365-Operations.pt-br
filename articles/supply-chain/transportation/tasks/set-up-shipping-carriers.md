---
title: Configurar transportadoras
description: Este tópico descreve como montar uma transportadora e definir detalhes como serviço, modo de envio, proposta de transporte, restrições de transporte e taxa de envio.
author: ShylaThompson
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 124f7473cbdae8890f74115d461603f50cc58be8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004868"
---
# <a name="set-up-shipping-carriers"></a>Configurar transportadoras

[!include [banner](../../includes/banner.md)]

Este tópico descreve como montar uma transportadora e definir detalhes como serviço, modo de envio, proposta de transporte, restrições de transporte e taxa de envio. Um coordenador de transporte pode então atribuir uma transportadora a uma carga de entrada ou de saída.


## <a name="create-a-new-shipping-carrier"></a>Crie uma nova transportadora
1. Acesse **Painel de navegação > Módulos > Gerenciamento de transporte > Configuração > Transportadoras > Transportadoras de envio**.
2. Selecione **Novo** no Painel de Ações.
3. No campo **Transportadora**, digite um valor.
4. No campo **Nome**, digite um valor.
5. No campo **Modo**, selecione uma opção no menu suspenso.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Preencha as informações gerais da transportadora
1. Ative a expansão da seção **Visão geral**.
2. Marque ou desmarque a caixa de seleção **Ativar a transportadora**.
3. No campo **Conta de Fornecedor**, selecione uma opção no menu suspenso. Selecione a conta do fornecedor para atribuí-la a transportadora.  
4. No campo **Tipo de proposta de transporte**, selecione uma opção. Selecione **Manual** para usar a página Proposta de Transporte, ou selecione **EDI** para atualizar a proposta usando Intercâmbio Eletrônico de Dados (EDI).  
5. Marque ou desmarque a caixa de seleção **Ativar a transportadora**.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Crie os serviços necessários para a transportadora
1. Ative a expansão da seção **Serviços**.
2. Selecione **Novo**.
3. No campo **Serviço da transportadora**, digite um valor.
4. No campo **Nome**, digite um valor.
5. No campo **Método de transporte**, selecione uma opção no menu suspenso.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Configure o endereço da transportadora (opcional)
1. Alternar a expansão da seção **Endereços**.
2. Selecione **Novo**.
3. No campo **Nome ou Descrição**, digite um valor.
4. No campo **País/região**, selecione uma opção no menu suspenso.
5. No campo **CEP/código postal de destino**, selecione uma opção no menu suspenso.
6. No campo **Rua**, digite um valor.
7. Selecione **OK**.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Configure o perfil de classificação para a transportadora.
1. Ative a expansão da seção **Perfis de classificação**.
2. Selecione **Novo**.
3. No campo **Perfil de classificação**, digite um valor.
4. No campo **Nome**, digite um valor.
5. No campo **Local**, selecione uma opção no menu suspenso.
6. No campo **Depósito**, selecione uma opção no menu suspenso.
7. No campo **Mecanismo de taxa**, selecione uma opção no menu suspenso. Selecione o Mecanismo de taxa que está de acordo com o contrato que você tem com a transportadora.  
8. No campo **Mestre de taxa**, selecione uma opção no menu suspenso.
9. No campo **Mecanismo de tempo em trânsito**, selecione uma opção no menu suspenso.
10. Selecione **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]