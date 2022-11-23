---
title: Configurar a importação avançada de reconciliação bancária usando Relatórios Eletrônicos
description: Este artigo explica como usar Relatório eletrônico para configurar o processo de importação de reconciliação bancária avançada.
author: angelad116
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
ms.openlocfilehash: bfc1c2021387ed35e6ccb513167e896eddef2eaf
ms.sourcegitcommit: ea79bf014bbf495ac8e28db29502c8bd85a75f32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2022
ms.locfileid: "9759591"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Configurar a importação avançada de reconciliação bancária usando Relatórios Eletrônicos

[!include [banner](../includes/banner.md)]

O recurso Reconciliação bancária avançada permite que você importe extratos bancários eletrônicos e os reconcilie automaticamente com as transações bancárias do Microsoft Dynamics 365 Finance. Este artigo explica como configurar a funcionalidade de importação para seus extratos bancários. A configuração de importação de extrato bancário varia de acordo com o formato do seu extrato bancário eletrônico. O Microsoft Dynamics 365 Finance oferece suporte a três formatos de extrato bancário: ISO20022, MT940 e BAI2. 

## <a name="set-up-the-electronic-reporting-configuration"></a>Definir a configuração do Relatório eletrônico

1. Acesse **Espaços de trabalho \> Relatório eletrônico**.
2. No bloco do provedor de configuração da **Microsoft**, selecione **Repositórios**.
3. Selecione **Global** e, em seguida, selecione **Abrir**.
4. Se for necessário estabelecer uma conexão com o repositório, selecione o link azul na caixa de diálogo.
5. Na lista configuração, localize **Modelo avançado de extrato de reconciliação bancária \> Formato ABR BAI2**.
6. Selecione o formato **BAI2**.
7. Na FastTab **Versões**, selecione a versão mais recente e depois **Importar**.

>[!NOTE]
>O **Modelo de extrato bancário de BAI2** será preterido em uma data posterior. 

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


## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exemplos de formatos de extrato bancário e layouts técnicos
Estes são exemplos das definições avançadas de layout técnico do arquivo de importação de reconciliação bancária e três arquivos de exemplo de extrato bancário relacionados: [Exemplos de arquivo de importação](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Definição do layout técnico                             | Arquivo de exemplo de extrato bancário          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)     |
| DynamicsAXISO20022Layout | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)     |

