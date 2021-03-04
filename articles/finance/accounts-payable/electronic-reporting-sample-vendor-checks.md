---
title: Amostra de relatório eletrônico para cheques de fornecedores
description: Este tópico fornece informações gerais sobre como usar a amostra de relatório eletrônico para formatos de cheque.
author: ShylaThompson
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a5c14f9529d11898e43f128c26859fc17fac9b73
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440462"
---
# <a name="electronic-reporting-sample-vendor-checks"></a>Amostra de relatório eletrônico para cheques de fornecedores

[!include [banner](../includes/banner.md)]

Você pode usar o ER (relatório eletrônico) para formatar cheques de fornecedores. Vários formatos de cheque específicos de provedores de cheque e de bancos estão disponíveis no mercado. As amostras de formato de cheque foram incluídas no Modelo de cheque de pagamento no repositório de ferramentas de ER. Essas amostras de cheque são rotuladas **Cheque no meio (EUA)** e **Cheque no stub superior abaixo (EUA)**.

## <a name="what-check-formats-are-currently-supported"></a>Atualmente há suporte para quais formatos de cheque?

Você sempre deve acessar a biblioteca de ativos compartilhados no Microsoft Dynamics Lifecycle Services (LCS) e exibir a lista atual de arquivos disponíveis que têm um tipo de ativo de **Configuração de GER**. A seção a seguir, "O que eu tenho que configurar?", inclui um link para um tópico que explica como criar um repositório LCS que possibilita a você revisar as configurações disponíveis e importar as configurações selecionadas.

O Microsoft Dynamics 365 Finance inclui um formato de exemplo no qual o cheque está na parte superior, seguido de duas seções de remessa. Também inclui um formato de amostra no qual o cheque está no meio, entre duas seções de remessa. Esses formatos de amostra correspondem aos formatos Deluxe Business Checks.

## <a name="what-do-i-have-to-set-up"></a>O que eu tenho que configurar?

- Antes de imprimir cheques usando o ER, ao menos uma configuração ativa do cheque deve ser importada para as suas configurações de ER. Para obter instruções, consulte [Baixar configurações do Relatório eletrônico no Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).
- Ao configurar os cheques de Gerenciamento de caixa e bancos para a conta bancária, marque a caixa de seleção **Formato de exportação eletrônico genérico** e, em seguida, selecione o formato de cheque apropriado como uma configuração de formato de exportação.
- Você também deve especificar o número de linhas de guia que serão impressas na remessa. Certifique-se de incluir as linhas de cabeçalho ao calcular esse número. Para ambas as amostras de formato de cheque, o número recomendado de linhas de guia é 17. Porém, esse número pode variar, dependendo do estoque de cheque e dos drivers de impressora.
- É recomendável imprimir um cheque de teste para validar o layout do cheque. Para imprimir um cheque de teste, selecione a opção **Imprimir teste**. Os formatos de cheque de exemplo funcionam melhor quando as **Margens** estão definidas como **Nenhuma** nas propriedades avançadas da impressora no Microsoft Excel. Após o cheque de teste ter sido gerado, habilite a edição da saída do Excel e configure o layout da página para que todas as margens sejam definidas como **0** (zero). Compare a cópia de teste dos cheques com o estoque de cheques e ajuste as configurações até ficar satisfeito com o alinhamento.
- Ao gerar pagamentos para a conta bancária configurada no diário de pagamento, os cheques serão impressos com o formato especificado.

Para obter mais informações, consulte [Modificar um formato de relatório eletrônico](../../dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]