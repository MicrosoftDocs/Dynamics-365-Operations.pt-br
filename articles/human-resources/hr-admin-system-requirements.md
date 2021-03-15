---
title: Requisitos do sistema
description: Este artigo descreve os requisitos do Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1e7d7389c1bcf0f6024464e37b36d39efae5b832
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111458"
---
# <a name="system-requirements"></a>Requisitos do sistema

Este artigo descreve os requisitos do Microsoft Dynamics 365 Human Resources. Ele também destaca os países e regiões onde Human Resources está disponível e informações sobre idiomas e localização dos dados do Human Resources.

## <a name="supported-web-browsers"></a>Navegadores da web suportados

O Human Resources pode ser executado em qualquer um dos navegadores da web que são executados nos sistemas operacionais especificados: 

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
> * O Human Resources é projetado para redes com latência de 250 a 300 milissegundos (ms) ou menos. Esta é a latência de um cliente de navegador para o data center do Microsoft Azure que hospeda o Human Resources. Recomendamos que você teste a latência de rede em [www.azurespeed.com](https://www.azurespeed.com "Teste de Latência do Azure").
> * Os requisitos de largura de banda do Human Resources depende do seu cenário. A maioria dos cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps).
> 
> [!WARNING]
> Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda. O uso simultâneo de um determinado local é muito difícil de calcular. Para clientes que estão preocupados com os requisitos de largura de banda, use uma versão de avaliação do Human Resources.

## <a name="supported-microsoft-office-applications"></a>Aplicativos Microsoft Office com suporte

* Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado. Para obter mais detalhes sobre os requisitos de versão, consulte [Solução de problemas de integração do Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Solução de problemas de integração do Office").
* Para exibir documentos que são gerados pela funcionalidade Exportar para o Excel ou Exportar para o Word, você deve ter o Microsoft Office 2007 ou posterior instalado.

## <a name="regional-availability-languages-and-localization"></a>Disponibilidade regional, idiomas e localização

Você pode baixar um arquivo PDF dos países, regiões e idiomas para os quais o Human Resources oferece suporte em [Disponibilidade internacional do Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability). 

> [!NOTE]
> Por mais que a interface de usuário esteja localizada em outros idiomas, todos os dados do usuário são armazenados no idioma no qual foi inserido. Você pode criar e-mails e modelos em outros idiomas, mas os dados como informações de agendamento só estão disponíveis em Inglês no momento.

Se você é um desenvolvedor interessado na criação de personalizações específicas do país ou região, ou em criar uma solução para um país ou região não suportado atualmente pela Microsoft, consulte [Globalização](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).


[!INCLUDE[footer-include](../includes/footer-banner.md)]