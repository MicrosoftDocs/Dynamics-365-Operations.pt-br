---
title: Configurar a importação avançada de reconciliação bancária usando Relatórios Eletrônicos
description: Este tópico explica como usar Relatórios Eletrônicos para configurar o processo de importação de reconciliação bancária avançada para demonstrativos de BAI2.
author: panolte
ms.date: 03/30/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 39f1d8ba561ab0e36346f1dfb4f70df318c92a37
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544465"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Configurar a importação avançada de reconciliação bancária usando Relatórios Eletrônicos

[!include [banner](../includes/banner.md)]

O recurso Reconciliação bancária avançada permite que você importe extratos bancários eletrônicos e os reconcilie automaticamente com as transações bancárias do Microsoft Dynamics 365 Finance. Este tópico explica como configurar a funcionalidade de importação para seus extratos bancários BAI2.

## <a name="set-up-the-electronic-reporting-configuration"></a>Definir a configuração do Relatório eletrônico

1. Acesse **Espaços de trabalho \> Relatório eletrônico**.
2. No bloco do provedor de configuração da **Microsoft**, selecione **Repositórios**.
3. Selecione **Global** e, em seguida, selecione **Abrir**.
4. Se for necessário estabelecer uma conexão com o repositório, selecione o link azul na caixa de diálogo.
5. Na lista configuração, localize o **Modelo de extrato bancário \> Modelo de extrato bancário de BAI2**.
6. Selecione o formato **BAI2**.
7. Na FastTab **Versões**, selecione a versão mais recente e depois **Importar**.

## <a name="set-up-the-bank-statement-format"></a>Configurar o formato de extrato bancário

1. Acesse **Gerenciamento de banco e caixa\> Configuração \> Configuração avançada de reconciliação bancária \> Formato do extrato bancário**.
2. Selecione **Novo**.
3. Defina os campos **Formato do demonstrativo** e **Nome**.
4. Marque a caixa de seleção **Formato de importação eletrônico genérico**.
5. Defina o campo **Importar configuração de formato** como o formato **BAI2**.

## <a name="set-up-the-bank-account"></a>Configurar a conta bancária

1. Acesse **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.
2. Abra a conta bancária.
3. Na guia rápida **Reconciliação**, defina a opção **Reconciliação bancária avançada** para **Sim**.
4. Defina o campo **Formato do extrato** como o formato criado anteriormente **BAI2**.

## <a name="import-the-bank-statement"></a>Importar o extrato bancário

1. Acesse **Gerenciamento de caixa e bancos \> Reconciliação de extrato bancário \> Extratos bancários**.
2. Na parte superior da página **Extratos bancários**, selecione **Importar demonstrativo**.
3. Defina o campo **Conta bancária** para a conta bancária do extrato.
4. Defina o campo **Formato do extrato** como o formato criado anteriormente **BAI2**.
5. Selecione **Procurar** e selecione o arquivo **BAI**.
6. Selecione **Carregar**.
7. Selecione **OK** para importar o arquivo selecionado.
