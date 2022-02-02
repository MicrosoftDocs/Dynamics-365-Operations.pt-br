---
title: Configurar números de conta bancária para o Brasil
description: Este tópico explica como configurar números de conta bancária para a localização brasileira.
author: gionoder
ms.date: 01/20/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Brazil
ms.author: gionoder
ms.search.validFrom: 2022-01-20
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1782dea573c104b9b977d9bdeb4e9043be82eb51
ms.sourcegitcommit: 68655c5673aef9892063e5913ffee6bfc3817387
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2022
ms.locfileid: "8016152"
---
# <a name="set-up-bank-account-numbers-for-brazil"></a>Configurar números de conta bancária para o Brasil

[!include [banner](../includes/banner.md)]

Quando você criar uma conta bancária, o número da conta bancária inserida deverá seguir um formato específico (máscara). Essa máscara inclui todos os atributos necessários para identificar um número de conta bancária de acordo com as regulamentações do Banco Central brasileiro.

Siga estas etapas para criar um número de conta bancária no formato necessário.

1. Acesse **Gerenciamento de Caixa e Bancos** > **Contas bancárias** > **Contas bancárias**.
2. Selecione uma conta bancária existente ou selecione **Nova** para criar uma nova conta bancária.
3. No campo **Número da conta bancária**, insira o número da conta bancária no seguinte formato:

    123 1234-1 012345678901-12

    Veja uma explicação dos dígitos na máscara:

    - **123** – o código do banco definido pelo Banco Central brasileiro.
    - **1234** – o número da agência bancária.
    - **1** – o dígito de verificação do número da agência bancária.
    - **012345678901** – o número da conta bancária.
    - **12** – o dígito de verificação do número da conta bancária.

    > [!IMPORTANT]
    > Os espaços entre o bloco de dígitos devem ser fornecidos de acordo com a máscara. Se o número da conta bancária inserida não seguir a máscara, você receberá a seguinte mensagem de validação: "Formato de conta bancária inválido. O formato esperado é "&lt;Código do banco&gt; &lt;número da agência&gt; &lt;número da conta&gt;"."
    >
    > O design de localização não extrai automaticamente os elementos do número da conta bancária do código IBAN (Número de Conta Bancária Internacional). Você deve extrair manualmente os elementos e inseri-los no campo **Número da conta bancária**.

4. Selecione **Salvar**.
