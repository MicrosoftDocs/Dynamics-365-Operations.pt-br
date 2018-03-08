---
title: Estender a funcionalidade do Microsoft Dynamics 365 for Talent
description: "Se você criou um Microsoft PowerApps, poderá iniciar esses aplicativos a partir de links do Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cfd3b475b113fdab4ceeb3e636fea6c9134ab982
ms.openlocfilehash: 0ab829803634871c9060daa381bd02d7d2bbdf42
ms.contentlocale: pt-br
ms.lasthandoff: 12/01/2017

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a>Estender a funcionalidade do Microsoft Dynamics 365 for Talent

[!include[banner](includes/banner.md)]

Se você criou um Microsoft PowerApps, poderá iniciar esses aplicativos a partir de links do Microsoft Dynamics 365 for Talent. Para configurar o acesso aos seus aplicativos, será necessário configurar as informações no Talent em uma página de configuração que você pode abrir no espaço de trabalho **Administração do sistema**.

## <a name="configuring-embedded-powerapps-within-talent"></a>Configurando o PowerApps inserido no Talent
Use a página **Configurar Microsoft PowerApps inserido** para configurar as páginas do Talent para iniciar os aplicativos do PowerApps. Para abrir a página **Configurar Microsoft PowerApps inserido**, abra o espaço de trabalho **Administração do sistema** e abra a guia **Links**. Selecione **Microsoft PowerApps** no grupo **Configuração**. 

As seguintes informações são inseridas ou configuradas nessa página: 

> - Um nome descritivo ou um identificador para cada aplicativo do PowerApps.
> - Um identificador exclusivo (GUID) para cada aplicativo adicionado a uma página do Talent. A ID do aplicativo está disponível no site de PowerApps [powerapps.com](http://powerapps.com/). 
> - A página da qual os usuários podem abrir um aplicativo ou relatório. Nem todas as páginas do Talent oferecem suporte a relatórios do Power BI ou do PowerApps inserido. 

 > [!NOTE]
 >  Insira o nome interno da página, e não o nome de exibição que é exibido na parte superior da página. Para encontrar o nome interno, abra a página da qual você precisa do nome interno e clique com o botão direito em qualquer lugar nela. Quando o menu abrir, passe o mouse sobre o item **Informações de formulário**. O nome do formulário interno será exibido ao lado do item **Informações do formulário** no menu.
 
> - Especifique o controle de formulário do qual o aplicativo pode recuperar dados de contexto. Por exemplo, um aplicativo pode usar dados sobre um trabalhador. Se você inserir a página **Trabalhador** no campo **Contexto**, a página **Trabalhador** abrirá quando você iniciar o aplicativo. Uma entrada no **Campo de contexto** é opcional. 
> - Defina o tamanho da caixa de diálogo na qual o aplicativo PowerApps será executado. As caixas de diálogo são designadas como "pequenas"ou “grandes” para otimizar a interface de usuário quando o aplicativo for executado em um telefone ou em um dispositivo maior, respectivamente. 

Também é possível especificar para quais entidades legais um aplicativo estará disponível, ou você pode disponibilizá-lo para todas as entidades legais. Por padrão, os aplicativos do PowerApps estão disponíveis para todas as entidades legais.

## <a name="opening-an-application"></a>Abrindo um aplicativo
Ao configurar os aplicativos do PowerApps inseridos, links para os aplicativos especificados serão adicionados às páginas no Talent. Clique em um link para abrir um aplicativo. 



