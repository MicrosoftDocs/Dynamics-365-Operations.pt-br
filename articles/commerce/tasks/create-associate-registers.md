---
title: Criar e associar registros
description: Este procedimento demonstra como criar um registro do ponto de venda (POS).
author: rubencdelgado
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba978a3d895394760687386197dbb3512c62ef98
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798552"
---
# <a name="create-and-associate-registers"></a>Criar e associar registros

[!include [banner](../includes/banner.md)]

Este procedimento demonstra como criar um registro do ponto de venda (POS). Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e Comércio > Configuração de canal > Configuração do PDV > Terminais.
2. Clique em Novo.
3. No campo Registrar número, digite uma ID para o novo registro.
    * A identificação do registro inclui tipicamente os códigos que ajudam a traçar o registro à loja que pertence e ao lugar dentro da loja.  
4. No campo Nome, digite um nome descritivo para o registro.
5. No campo Número da loja, insira ou selecione um valor.
6. No campo Perfil de hardware, insira ou selecione um valor.
    * Os perfis de hardware são usados para especificar os periféricos que serão conectados ao registro, tal como o caixa do dinheiro e a impressora do recibo.  
7. No campo Perfil visual, insira ou selecione um valor.
    * Os perfis visuais são usados para especificar as imagens usadas no fundo da posição e na página do início de uma sessão assim como temas para a posição.  
8. No campo Número do registro de PDV de TEF, digite um valor.
    * O número do registro da posição de EFT é usado para informar o processador do pagamento ao qual o terminal do pagamento está enviando pedidos da autorização. Este valor é chamado frequentemente de "ID de terminal ou "TID". O TID pode geralmente ser encontrado em uma etiqueta no dispositivo do pagamento.  
9. Clique em Salvar.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]