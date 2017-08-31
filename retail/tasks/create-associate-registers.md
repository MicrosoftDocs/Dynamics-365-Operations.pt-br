--- 
title: " Criar e associar registros"
description: Este procedimento demonstra como criar um registro do ponto de venda (POS).
author: rubencdelgado
manager: AnnBe
ms.date: 10/05/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: c49b42ae4ef7505c48fc50cdf7c7e9800c248ec6
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="create-and-associate-registers"></a> Criar e associar registros

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento demonstra como criar um registro do ponto de venda (POS). Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e comércio > Configuração do canal > Configuração do PDV > Registros.
2. Clique em Novo.
3. No campo Registrar número, digite uma ID para o novo registro.
    * A identificação do registro inclui tipicamente os códigos que ajudam a traçar o registro à loja que pertence e ao lugar dentro da loja.  
4. No campo Nome, digite um nome descritivo para o registro.
5. No campo Número da loja, insira ou selecione um valor.
6. No campo Perfil de hardware, insira ou selecione um valor.
    * Os perfis de hardware são usados para especificar os periféricos de varejo que serão conectados ao registro, tal como o caixa do dinheiro e a impressora do recibo.  
7. No campo Perfil visual, insira ou selecione um valor.
    * Os perfis visuais são usados para especificar as imagens usadas no fundo da posição e na página do início de uma sessão assim como temas para a posição.  
8. No campo Número do registro de PDV de TEF, digite um valor.
    * O número do registro da posição de EFT é usado para informar o processador do pagamento ao qual o terminal do pagamento está enviando pedidos da autorização. Este valor é chamado frequentemente de "ID de terminal ou "TID". O TID pode geralmente ser encontrado em uma etiqueta no dispositivo do pagamento.  
9. Clique em Salvar.


