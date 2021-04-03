---
title: Solucionar problemas do Conector de Pagamento do Dynamics 365 para Adyen
description: Este tópico fornece diretrizes de solução de problemas que podem ajudá-lo a obter suporte quando tiver problemas com o Conector de Pagamento do Microsoft Dynamics 365 para Adyen.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f01db3fa670355696c094be544775a3abc557a70
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585188"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a>Solucionar problemas do Conector de Pagamento do Dynamics 365 para Adyen

[!include [banner](../../includes/banner.md)]

Este tópico fornece diretrizes de solução de problemas que podem ajudá-lo a obter suporte quando tiver problemas com o Conector de Pagamento do Microsoft Dynamics 365 para Adyen.

## <a name="description"></a>descrição

Você tem problemas com o Conector de Pagamento do Dynamics 365 para Adyen nas seguintes áreas e precisa de suporte da equipe da Adyen:

- Configuração do PDV (Ponto de venda), Modern point of sale (MPOS), call center ou Dynamics 365 Commerce
- O número de referência do Provedor de serviço de pagamento Adyen (PSP) (por exemplo, se tiver perguntas sobre as recusas, incluindo recusas de entrada de chave manual \[MKE\])
- Tudo o que não estiver funcionando em ambientes de teste ou de comerciante dinâmicos

## <a name="resolution"></a>Resolução

Use o modelo de email a seguir para iniciar o processo de suporte da equipe da Adyen. Para acelerar a solução de problemas, verifique se o email contém todos os detalhes necessários.

| Campo        | Alíquota |
|--------------|-------|
| Até           | `support@adyen.com` |
| Cc           | |
| Linha do assunto | Solicitação de suporte do Microsoft Dynamics |
| Corpo         | <p>Olá, Suporte,</p><p>Forneça suporte para o seguinte problema:</p><ul><li>Conta de comerciante</li><li>Ambiente (Teste/Produção)</li><li>Canal (PDV/call center/Comércio eletrônico do Commerce)</li><li>O número de referência PSP, se o problema envolvido em uma transação específica (você pode encontrar o número de referência PSP no recibo, na Área de Cliente da Adyen ou no menu transações no terminal de PDV).</li><li>Captura de tela ou foto da mensagem de erro, se aplicável</li><li>Logs do Visualizador de Eventos (no formato .txt)</li><li>Descrição da questão e das etapas de solução de problemas que você tentou</li></ul> |

## <a name="additional-resources"></a>Recursos adicionais

[Aceitar pagamentos com o conector da Adyen para Dynamics 365 Commerce](https://www.adyen.com/partners/dynamics-365-commerce)

[Conector de Pagamento do Dynamics 365 para Adyen](../dev-itpro/adyen-connector.md)

[Configurar o conector de pagamento da Adyen para Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
