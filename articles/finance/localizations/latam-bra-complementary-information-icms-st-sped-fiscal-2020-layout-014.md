---
title: SPED fiscal 2020 - informações complementares do ICMS-ST para o layout 014 do SPED fiscal 2020
description: Este tópico fornece informações sobre como utilizar o complemento e a compensação do ICMS-ST para o ano civil de 2020.
author: gionoder
manager: AnnBe
ms.date: 12/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 972961647d24e45a05f86a21544319a4226b6572
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408456"
---
# <a name="sped-fiscal-2020---complementary-information-of-the-icms-st-for-sped-fiscal-2020-layout-014"></a>SPED fiscal 2020 - informações complementares do ICMS-ST para o layout 014 do SPED fiscal 2020

[!include [banner](../includes/banner.md)]

Quando uma empresa desejar utilizar o complemento e a compensação do ICMS-ST para o ano civil de 2020, ela precisará começar a registrar as informações adicionais do ICMS-ST durante o recebimento do modelo 55 de notas fiscais eletrônicas, a partir de 1º de janeiro de 2020.

Somente para o Dynamics 365 Finance, esse recurso deve ser habilitado usando o Gerenciamento de Recursos. Conclua as seguintes etapas para habilitar esse recurso.

1. No Finance, no painel **Início**, selecione **Gerenciamento de Recursos**.
3. Procure e selecione *Informações complementares do ICMS-ST*.
4. Selecione **Habilitar agora**.

Quando a nota fiscal de fornecedor ou de transferência incluir um produto sujeito à tributação ICMS-ST na UF (estado) do endereço de destino, e se o estabelecimento fiscal de recebimento utilizar o complemento e a compensação do ICMS-ST, os seguintes atributos da nota fiscal devem ser inseridos.

- O participante responsável pela retenção do ICMS-ST:
        
    - **Direto** - quando um emissor de estabelecimento fiscal ou de terceiros da nota fiscal é diretamente responsável pela retenção do ICMS-ST para o produto presente na nota fiscal.
    - **Indireto** - quando um emissor de estabelecimento fiscal ou de terceiros da nota fiscal já recebeu o produto e o ICMS-ST foi retido de sua cadeia de fornecedores.
    - **Próprio declarante** - quando o estabelecimento fiscal de recebimento é responsável pela retenção do ICMS-ST que deveria ter sido retido pelo emissor de terceiros, mas não foi.
    
- O modo de pagamento de coleta do ICMS-ST:
        
    - **Documento do estado da coleta** - quando o ICMS-ST é retido por meio da apuração de imposto ICMS-ST regular e o pagamento ocorre após o final do período da transação.
    - **GNRE** - quando a nota fiscal de recebimento é acompanhada por um GNRE que mostra que o ICMS-ST devido já foi retido e pago pelo emissor da nota fiscal quando o documento foi gerado.
    
- O número de pagamento de coleta do ICMS-ST: 
    - O número de GNRE usado para liquidar o valor do pagamento do ICMS-ST pelo emissor da nota fiscal.

Quando uma linha de nota fiscal incluir um produto sujeito ao ICMS-ST no destino de recebimento, a retenção do ICMS-ST será determinada analisando o código de tributação do ICMS-ST na nota fiscal de recebimento. Isso é comparado à linha equivalente do ICMS-ST no XML da NF-e emitida pelo remetente da nota fiscal.

![GSTINs anexados a um grupo de registro de impostos com código de tributação indireta](media/complementary-info-figure-01.PNG)

![GSTINs anexados a um grupo de registro de impostos com código de tributação direta](media/complementary-info-figure-02.PNG)

Um valor padrão para o campo **Responsável pela retenção do ICMS-ST** pode ser configurado concluindo as etapas a seguir.

1. Acesse **Imposto** > **Configurar** > **Imposto sobre vendas** > **Responsável pela retenção do ICMS-ST**.
2. No campo **Código CFOP**, selecione **Tabela**, **Grupo** ou **Tudo**.
3. No campo **Relação CFOP**, insira a relação definida pelo Código CFOP.
4. No campo **Emissor da nota fiscal**, selecione **Estabelecimento fiscal** ou **Terceiro** para definir a origem da nota fiscal.
5. No campo **Código de tributação do destinatário**, insira o código de tributação do ICMS-ST configurado para a linha de nota fiscal de recebimento na qual o produto está sujeito à substituição tributária do ICMS.
6. No campo **Código de tributação do remetente**, insira o código de tributação do ICMS-ST presente na linha de nota fiscal do emissor na qual o produto está sujeito à substituição tributária do ICMS.
7. Para uma relação CFOP e um Emissor da nota fiscal, e com base na relação entre o **Código de tributação do destinatário** e o **Código de tributação do remetente**, no campo **Responsável pela retenção do ICMS-ST**, selecione **Direto**, **Indireto** ou **Próprio declarante**.

Os novos campos, **Responsável pela retenção do ICMS-ST**, **Modo de pagamento de coleta do ICMS-ST** e **Número de pagamento de coleta do ICMS-ST**, estão incluídos nas seguintes páginas:

- Página **Faturas de fornecedor** na guia **Informações fiscais**.
- Página **Ordem de transferência** na guia **Informações fiscais de recebimento**.
- Página **Fatura de cliente** na guia **Informações fiscais**. Isso é somente para devoluções de clientes.

> [!NOTE]
> Durante o recebimento de uma nota fiscal, quando o ICMS-ST é tributável usando o código de tributação 10, apesar de estarem inseridas no campo **Responsável pela retenção do ICMS-ST**, as informações financeiras e de avaliação de custo não são incluídas no escopo da localização.
