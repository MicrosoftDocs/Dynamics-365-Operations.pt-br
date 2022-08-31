---
title: NT2021.004 – atualizações de layout e validação na nota fiscal eletrônica (NF-e)
description: Este artigo fornece informações sobre as atualizações no layout XML e regras de validação na nota técnica NT2021.004.
author: gionoder
ms.date: 08/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: gionoder
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 0eaf8cf5d92d1381322ca74127303d4171f5702e
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9326712"
---
# <a name="nt2021004--layout-and-validation-updates-in-the-electronic-fiscal-document-nf-e"></a>NT2021.004 – atualizações de layout e validação na nota fiscal eletrônica (NF-e)

[!include [banner](../includes/banner.md)]

Este artigo descreve as atualizações no layout XML e regras de validação que foram introduzidas pela nota técnica NT2021.004 para a geração da nota fiscal eletrônica modelo 55 (NF-e).

## <a name="enable-the-technical-note-in-dynamics-365-finance-and-dynamics-365-supply-chain-management"></a>Habilitar a nota técnica no Dynamics 365 Finance e Dynamics 365 Supply Chain Management

1. Entre na sua instância do Microsoft Dynamics 365 Finance ou do Dynamics 365 Supply Chain Management.
2. Acesse **Administração da organização** \> **Organizações** \> **Estabelecimentos fiscais** \> **Estabelecimentos fiscais**.
3. Selecione o estabelecimento fiscal e, depois, selecione **Editar**.
4. Na guia **NF-e e NFC-e federal**, na seção **Notas técnicas da NF-e**, selecione **Habilitar nota técnica de NF-e**.
5. No campo **Notas técnicas da NF-e**, selecione **Nota técnica 2021.004 v1.00**.
6. Selecione **Salvar**.

## <a name="scope-for-version-100-of-the-technical-note"></a>Escopo da versão 1.00 da nota técnica

Essa nota técnica apresentou uma nova marca usada para enviar as informações sobre a lei de concessão. A marca é aplicável somente quando o órgão do processo referido é a SEFAZ (autoridade fiscal brasileira). Essa nota técnica também apresentou novas regras de validação para aplicar o uso correto das informações de frete no XML.

### <a name="updates-in-the-xml"></a>Atualizações no XML

#### <a name="new-lttpatogt-tag"></a>Nova marca &lt;tpAto&gt;

Novas opções são adicionadas aos textos de origem da nota fiscal para habilitar a configuração do tipo de lei de concessão, de forma que a nova marca **&lt;tpAto&gt;** possa ser preenchida em cenários em que o valor da **Agência** é **SEFAZ**.

1. Acesse **Administração da organização** \> **Organizações** \> **Configuração** \> **Textos de origem da nota fiscal**.
2. Selecione um texto de origem da nota fiscal.
3. Na guia **Processo referenciado**, selecione **Novo**.
4. Na coluna **Agência**, selecione **SEFAZ**.
5. Insira o número do processo referenciado.
6. No campo **Tipo de lei de concessão**, selecione o tipo de lei de concessão, conforme definido na nota técnica.
7. Selecione **Salvar**.

## <a name="scope-for-version-131-of-the-technical-note"></a>Escopo da versão 1.31 da nota técnica

### <a name="updates-in-validation-rules"></a>Atualizações em regras de validação

Novas regras de validação são atualizadas durante o lançamento de notas fiscais para ajudar a evitar os seguintes códigos de erro de rejeição de NF-e:

- 847
- 849

Durante o lançamento de notas fiscais eletrônicas de saída, quando a marca **&lt;tpNF&gt;** é igual a **1** (de saída):

- Se a ID de registro de imposto (CNPJ base) do transportador for igual à ID de registro de imposto (CNPJ base) do emissor, as condições de encargos de frete deverão ser diferentes de **Pré-pago** (**modFrete** = **0**). Caso contrário, a regra de validação X04-50 será violada.
- Se a ID de registro de imposto (CNPJ base) do transportador for igual à ID de registro de imposto (CNPJ base) do receptor, as condições de encargos de frete deverão ser diferentes de **Cobrar** (**modFrete** = **1**). Caso contrário, a regra de validação X04-90 será violada.

Durante o lançamento de notas fiscais eletrônicas de entrada, quando a marca **&lt;tpNF&gt;** é igual a **0** (de entrada):

- Se a ID de registro de imposto (CNPJ base) do transportador for igual à ID de registro de imposto (CNPJ base) do emissor, as condições de encargos de frete deverão ser diferentes de **Cobrar** (**modFrete** = **1**). Caso contrário, a regra de validação X04-100 será violada.
- Se a ID de registro de imposto (CNPJ base) do transportador for igual à ID de registro de imposto (CNPJ base) do receptor, as condições de encargos de frete deverão ser diferentes de **Pré-pago** (**modFrete** = **0**). Caso contrário, a regra de validação X04-60 será violada.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
