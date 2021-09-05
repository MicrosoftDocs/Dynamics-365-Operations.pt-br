---
title: Requisitos do sistema
description: Este tópico lista os requisitos do sistema do Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15770595a0639c03df1138ec25010ca8168bd9a8
ms.sourcegitcommit: 49f7528d3268abe15e40f719956e1ec8696a6f4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2021
ms.locfileid: "7393464"
---
# <a name="system-requirements"></a>Requisitos do sistema

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico lista os requisitos do sistema do Microsoft Dynamics 365 Human Resources. Ele também destaca os países e regiões onde Human Resources está disponível e informações sobre idiomas e localização dos dados do Human Resources.

## <a name="supported-web-browsers"></a>Navegadores da web suportados

Os usuários podem acessar o Microsoft Dynamics 365 Human Resources usando qualquer um dos navegadores da Web que são executados nos sistemas operacionais especificados: 

*   Microsoft Edge (última versão disponível publicamente) no Windows 10
*   Internet Explorer 11 no Windows 10, Windows 8.1 ou Windows 7
*   Google Chrome (última versão disponível publicamente)
*   Apple Safari (última versão disponível publicamente)

Para localizar a versão mais recente de cada navegador, Acesse o site do fabricante do software. 

## <a name="special-considerations"></a>Considerações especiais

* Para ativar o Gravador de Tarefas para obter capturas de tela e incluí-las nos documentos do Microsoft Word que são gerados, você deve instalar uma extensão do Chrome de pré-lançamento
* O editor de fluxo de trabalho é iniciado como um aplicativo ClickOnce. Apenas o Microsoft Edge e o Internet Explorer (em uma versão compatível do Microsoft Windows) são compatíveis com os aplicativos ClickOnces. O aplicativo Editor de fluxo de trabalho ClickOnce requer um sistema operacional compatível com 64 bits.
* Para visualizar os arquivos PDF, recomendamos que você use navegadores modernos como o Microsoft Edge (última versão disponível publicamente) no Windows 10 ou o Google Chrome (última versão disponível publicamente) no Windows 10, Windows 8.1, Windows 8, Windows 7 ou no tablet Google Nexus 10.

## <a name="network-requirements"></a>Requisitos de rede

* O Human Resources é projetado para redes com latência de 250 a 300 milissegundos (ms) ou menos. Esta é a latência de um cliente de navegador para o data center do Microsoft Azure que hospeda o Human Resources. Recomendamos que você teste a latência de rede em [www.azurespeed.com](https://www.azurespeed.com "Teste de Latência do Azure").
* Os requisitos de largura de banda do Human Resources depende do seu cenário. Os cenários típicos requerem uma largura de banda de mais de 50 kilobytes por segundo (KBps).
 
> [!WARNING]
> Não calcule os requisitos de largura de banda de um local de cliente multiplicando o número de usuários pelos requisitos mínimos de largura de banda. O uso simultâneo de um determinado local é muito difícil de calcular. Para clientes que estão preocupados com os requisitos de largura de banda, use uma versão de avaliação do Human Resources.

## <a name="supported-microsoft-office-applications"></a>Aplicativos Microsoft Office com suporte

* Para executar os suplementos do Microsoft Excel e Word, você deve ter o Microsoft Office 2016 para Windows ou Mac instalado. Para obter mais detalhes sobre os requisitos de versão, consulte [Solução de problemas de integração do Office](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md "Solução de problemas de integração do Office").
* Para exibir documentos que são gerados pela funcionalidade Exportar para o Excel ou Exportar para o Word, você deve ter o Microsoft Office 2007 ou posterior instalado.

## <a name="regional-availability-languages-and-localization"></a>Disponibilidade regional, idiomas e localização

Você pode baixar um arquivo PDF dos países, regiões e idiomas para os quais o Human Resources oferece suporte em [Disponibilidade internacional do Microsoft Dynamics 365](/dynamics365/get-started/availability). 

> [!NOTE]
> Por mais que a interface de usuário esteja localizada em outros idiomas, todos os dados do usuário são armazenados no idioma no qual foi inserido. Você pode criar e-mails e modelos em outros idiomas, mas os dados como informações de agendamento só estão disponíveis em Inglês no momento.

Se você é um desenvolvedor interessado na criação de personalizações específicas do país ou região, ou em criar uma solução para um país ou região não suportado atualmente pela Microsoft, consulte [Globalização](/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
