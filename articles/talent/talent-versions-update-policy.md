---
title: Requisitos do sistema e política de atualização do Talent
description: Este tópico lista os requisitos do Dynamics 365 for Talent. A política de atualização também está descrita.
author: andreabichsel
manager: AnnBe
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6c881bf25e7145228ccf7ef73a7ef3637c115a49
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741766"
---
# <a name="talent-system-requirements-and-update-policy"></a>Requisitos do sistema e política de atualização do Talent

[!include [banner](includes/banner.md)]

Este tópico descreve os requisitos do Microsoft Dynamics 365 for Talent, incluindo Attract, Onboard e Core HR. Ele também destaca os países e regiões onde Talent está disponível, além de informações sobre idiomas e localização dos dados do Talent. Além disso, este tópico fornece a política atualizada para o Talent.

## <a name="supported-web-browsers"></a>Navegadores da web suportados

O aplicativo da web do Microsoft Dynamics 365 for Talent pode ser executado em qualquer um dos navegadores da web que são executados nos sistemas operacionais especificados: 

*   Microsoft Edge (última versão disponível publicamente) no Windows 10
*   Internet Explorer 11 no Windows 10, Windows 8.1 ou Windows 7
*   Google Chrome (última versão disponível publicamente)
*   Apple Safari (última versão disponível publicamente)

Para localizar a versão mais recente de cada navegador, vá para o site do fabricante do software. 

> [!NOTE]
> * Para capturar imagens geradas a partir do Gravador de Tarefas e incluí-las em documentos do Microsoft Word, você deve ter uma extensão do Chrome instalada. 
> * O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce. Apenas o Microsoft Edge e o Internet Explorer (em uma versão compatível do Microsoft Windows) são compatíveis com os aplicativos ClickOnces. O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.
> * Para visualizar os arquivos PDF, recomendamos que você use navegadores modernos como o Microsoft Edge (última versão disponível publicamente) no Windows 10 ou o Google Chrome (última versão disponível publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou no tablet Google Nexus 10.
>   Requisitos de rede
> * O Dynamics 365 for Talent é projetado para redes com latência de 250 a 300 milissegundos (ms) ou menos. Esta é a latência de um cliente de navegador para o centro de dados do Microsoft Azureque hospeda o Dynamics 365 for Talent. Recomendamos que você teste a latência de rede em [www.azurespeed.com](https://www.azurespeed.com "Teste de latência do Azure").
> * Os requisitos de largura de banda do Dynamics 365 for Talent dependem do seu cenário. A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps).
> 
> [!WARNING]
> Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda. O uso simultâneo de um determinado local é muito difícil de calcular. Para clientes que estão preocupados com os requisitos de largura de banda, use uma versão de avaliação do Dynamics 365 for Talent.

## <a name="supported-microsoft-office-applications"></a>Aplicativos Microsoft Office com suporte

* Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado. Para obter mais detalhes sobre requisitos de versão, consulte [Solução de problemas de integração do Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Solução de problemas de integração do Office").
* Para exibir documentos que são gerados pela funcionalidade Exportar para o Excel ou Exportar para o Word, você deve ter o Microsoft Office 2007 ou posterior instalado.

## <a name="regional-availability-languages-and-localization"></a>Disponibilidade regional, idiomas e localização

Você pode baixar um arquivo PDF dos países, regiões e idiomas para os quais Talent oferece suporte em [Disponibilidade internacional do Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability). 

> [!NOTE]
> Por mais que a interface de usuário esteja localizada em outros idiomas, todos os dados do usuário são armazenados no idioma no qual foi inserido. Você pode criar e-mails e modelos em outros idiomas, mas os dados como informações de agendamento só estão disponíveis em Inglês no momento.

Se você é um desenvolvedor interessado na criação de personalizações específicas do país ou região, ou em criar uma solução para um país ou região não suportado atualmente pela Microsoft, consulte [Globalização](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

## <a name="update-policy"></a>Política de atualização

O Dynamics 365 for Talent é apresentado como uma oferta da nuvem. As atualizações do Dynamics 365 for Talent são contínuas e são aplicadas automaticamente pela Microsoft.

As atualizações são liberadas em uma cadência normal e serão feitas em todos os ambientes. O Dynamics 365 for Talent é compatível de acordo com a [política de Ciclo de Vida de Suporte da Microsoft](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Ciclo de Vida de Suporte da Microsoft"), que oferece diretrizes consistentes e previsíveis para a disponibilidade do suporte a produtos.
