---
title: Configurar e gerar arquivos de pagamento positivos usando Relatório eletrônico
description: Este tópico explica como configurar o pagamento positivo usando o Relatório eletrônico.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 43dd1a9cba1fe8df5cff26fe76af7e2957a0d6a4
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544456"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Configurar arquivos de pagamento positivos usando o Relatório eletrônico

Configure o pagamento positivo para gerar uma lista eletrônica de cheques que é fornecida ao banco. Então, quando o cheque é apresentado ao banco, o banco o compara à lista de cheques. Se o cheque corresponder a um cheque na lista, o banco o liberará. Se o cheque não corresponder a um cheque na lista, o banco o reterá para revisão.

## <a name="set-up-the-electronic-reporting-configuration"></a>Definir a configuração do Relatório eletrônico

1. Acesse **Espaços de trabalho \> Relatório eletrônico**.
2. No bloco do provedor de configuração da **Microsoft**, selecione **Repositórios**.
3. Selecione **Global** e, em seguida, selecione **Abrir**.
4. Se for necessário estabelecer uma conexão com o repositório, selecione o link azul na caixa de diálogo.
5. Na lista de configuração, localize e selecione o **formato de pagamento positivo \> do modelo de pagamento positivo**.
6. Na FastTab **Versões**, selecione a versão mais recente e depois **Importar**.

## <a name="set-up-a-positive-pay-format"></a>Configurar um formato de pagamento positivo

1. Acesse **Gerenciamento de caixa e bancos \> Configuração \> Formatos de pagamento positivo**.
2. Selecione **Novo**.
3. Defina os campos **Formato de pagamento** e **Descrição**.
4. Marque a caixa de seleção **Formato de exportação eletrônico genérico**.
5. Defina o campo **Exportar configuração de formato** como **Formato de pagamento positivo**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Atribuir um formato de pagamento positivo a uma conta bancária

1. Acesse **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.
2. Abra a conta bancária.
3. Na FastTab **Geral**, defina o campo **Formato de pagamento positivo** como o formato que foi criado anteriormente.
4. Defina o campo **Data de início do pagamento positivo** como a data atual.

## <a name="generate-a-positive-pay-file"></a>Gerar um arquivo de pagamento positivo

1. Acesse **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias**.
2. Abra uma conta bancária para a qual o pagamento positivo está configurado.
3. Selecione **Gerenciar pagamentos \> Pagamento positivo \> Arquivo de pagamento positivo**.
4. Defina o campo **Data de fechamento**. Os cheques que foram gerados antes dessa data serão incluídos.

O arquivo XML resultante será baixado.
