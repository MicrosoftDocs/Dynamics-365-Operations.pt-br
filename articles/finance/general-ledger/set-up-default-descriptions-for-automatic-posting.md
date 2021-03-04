---
title: Configurar descrições padrão para lançamento automático
description: Este tópico explica como configurar o texto padrão que é usado para descrever entradas de contabilidade lançadas automaticamente na contabilidade. Você pode configurar o texto padrão de descrição usando o texto livre ou selecionando variáveis fixas.
author: aprilolson
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f5fc73f636a5cac25c259ce2cbae5c5407dca9b7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440182"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a>Configurar descrições padrão para lançamento automático

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar o texto padrão que é usado para descrever entradas de contabilidade lançadas automaticamente na contabilidade. Você pode configurar o texto padrão de descrição usando o texto livre ou selecionando variáveis fixas.

> [!NOTE]
> Para determinados tipos de transação em alguns países ou regiões, também é possível incluir o texto dos campos no banco de dados Microsoft Dynamics AX que estão relacionados a esses tipos de transação. Para obter uma lista de tipos de transação, além de países e regiões, consulte a seção [Opcional: adicionar texto às descrições padrão](#optional-add-other-text-to-default-descriptions) posteriormente neste tópico.

## <a name="set-up-default-descriptions"></a>Configurar descrições padrão

1. Vá para **Administração da organização** \> **Configuração** \> **Descrições padrão**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **Descrição**, selecione o tipo de transação para o qual uma descrição padrão será criada.
4. No campo **Idioma**, selecione o idioma para o qual esta descrição será aplicada.
5. No campo **Texto**, insira uma descrição padrão. Você pode digitar o texto no campo ou usar uma ou mais das seguintes variáveis de texto livre:

    - **%1** – adicione a data de transação.
    - **%2** – adiciona um identificador que corresponde ao tipo de documento que está sendo lançado na contabilidade. Por exemplo, para os tipos de transação relacionados a faturas, a variável **%2** adiciona o número da fatura.
    - **%3** – adicione um identificador relacionado ao tipo de documento que está sendo lançado na contabilidade. Por exemplo, para os tipos de transação relacionados a faturas, a variável **%3** adiciona o número de conta do cliente.

## <a name="optional-add-other-text-to-default-descriptions"></a>Opcional: Adicionar outro texto para descrições padrão

Para determinados tipos de transação em alguns países ou algumas regiões, é possível incluir o texto em suas descrições padrão que vem dos campos no seus dados que estão relacionados a esses tipos de transação. As listas a seguir mostram os tipos de transação, os países e as regiões para os quais esta opção está disponível.

**Tipos de transação**

Você pode adicionar outras descrições de texto padrão para os tipos de transação relacionados aos seguintes tipos de documento:

- Faturas de clientes
- Notas de crédito de clientes
- Pagamentos à vista de clientes
- Pagamentos de fornecedores
- Ordens de venda
- Ordens de compra
- Diários de estoque
- Planejamento mestre (MRP)
- Ativos fixos

**Países e regiões**

Essa opção está disponível somente para os seguintes países e regiões:

- Brasil
- China
- República Tcheca
- Leste Europeu
- Hungria
- Índia
- Japão
- Lituânia
- Letônia
- Polônia
- Rússia

### <a name="add-text-to-default-descriptions"></a>Adicionar texto às descrições padrão

Depois de concluir as etapas na seção [Definir descrições padrão](#set-up-default-descriptions), anteriormente neste tópico, siga estas etapas para adicionar outro texto para as descrições padrão.

1. Na Guia Rápida **Parâmetros**, selecione **Adicionar**.
2. No campo **Tabela de referência**, selecione a tabela de banco de dados da qual os dados de parâmetros serão adicionados à descrição.
3. No campo **Tabela de referência**, selecione o campo do qual os dados de parâmetros serão adicionados à descrição.
4. Repita as etapas 1 a 3 para adicionar mais parâmetros.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]