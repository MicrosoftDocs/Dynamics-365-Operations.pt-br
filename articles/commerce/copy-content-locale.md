---
title: Copiar conteúdo para outra localidade
description: Este artigo descreve como copiar conteúdo existente para outra localidade em um site no construtor de sites do Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 07/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: bcfa3c7cb2ea8018422803d85df6b6761b8d1145
ms.sourcegitcommit: d719d0a549aecac231fad0abb42250eab9dd0ded
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2022
ms.locfileid: "9126443"
---
# <a name="copy-content-to-another-locale"></a>Copiar conteúdo para outra localidade

[!include[banner](../includes/banner.md)]

Este artigo descreve como copiar conteúdo existente para outra localidade em um site no construtor de sites do Microsoft Dynamics 365 Commerce.

Quando você cria conteúdo no construtor de sites do Commerce, ele sempre é associado a um identificador de localidade; por exemplo, "en-US". Você pode copiar páginas e ativos individuais para uma localidade diferente no mesmo site de comércio eletrônico trocando a localidade ao editar um item de conteúdo e criando uma nova variante do item. Em alguns casos, por exemplo, quando você está lançando uma localidade totalmente nova na sua vitrine, faz sentido duplicar todos os itens de conteúdo em uma localidade existente para a nova localidade. Se a nova localidade tiver o mesmo idioma base que uma das localidades existentes, você poderá usar a localidade existente como a localidade de origem para a operação de cópia da localidade. (Por exemplo, as localidades "en-us" e "en-au" usam o idioma inglês.) Dessa forma, você ajuda a reduzir o esforço necessário para localizar o conteúdo na nova localidade.

Os procedimentos a seguir explicam como adicionar uma nova localidade a um canal existente, copiar todos os itens de conteúdo de uma localidade existente para uma nova localidade e monitorar o status de uma operação de cópia da localidade.

## <a name="add-a-new-locale"></a>Adicionar uma nova localidade

Para adicionar uma nova localidade no criador de sites do Commerce, siga estas etapas.

1. No construtor de sites, navegue até o seu site.
1. No painel de navegação esquerdo, selecione **Configurações do site** e selecione **Canais**.
1. Em **Canal**, selecione o canal ao qual a nova localidade será adicionada.
1. Na caixa de diálogo canal que aparece à direita, selecione **Adicionar uma localidade**.
1. Na caixa de diálogo **Adicionar uma localidade**, no campo **Localidade para suporte**, selecione uma localidade.
1. Confirme se o valor de **Domínio** está correto.
1. Em **Caminho**, digite um caminho de URL exclusivo (por exemplo, **en-us** ou **english-us**).
1. Selecione **OK**.
1. Feche a caixa de diálogo do canal.
1. Em **Canal**, confirme se a nova localidade está listada ao lado do canal correto.
1. Selecione **Salvar e publicar**.

> [!NOTE]
> Antes que a nova localidade possa ser configurada no construtor de sites, ela deve ser adicionada ao canal de loja online associado no Commerce headquarters.

## <a name="copy-all-content-items-to-a-new-locale"></a>Copiar todos os itens de conteúdo para uma nova localidade

Para copiar todos os itens de conteúdo para uma nova localidade no construtor de sites do Commerce, siga estas etapas.

1. No construtor de sites, navegue até o seu site.
1. No painel de navegação esquerdo, selecione **Configurações do site** e selecione **Canais**.
1. Na barra de comandos, selecione **Criar cópia da localidade de**.
1. Na caixa de diálogo **Criar cópia da localidade** que aparece à direita, em **Site de origem**, confirme se o site correto está selecionado.
1. No campo **Canal de origem**, selecione o canal de origem.
1. No campo **Canal de destino**, selecione o mesmo canal de origem.
1. No campo **Localidade de origem**, selecione a localidade de origem.
1. No campo **Localidade de destino**, selecione a nova localidade.
1. Selecione **Copiar localidade**. Uma notificação confirma que a operação de cópia de localidade foi iniciada.

> [!NOTE]
> Você também pode copiar o conteúdo entre canais diferentes.

## <a name="monitor-the-status-of-the-locale-copy"></a>Monitorar o status da cópia de localidade

Para monitorar o status de uma operação de cópia de localidade, siga estas etapas.

1. No construtor de sites, navegue até o seu site.
1. No painel de navegação esquerdo, selecione **Configurações do site** e selecione **Trabalhos**.
1. Em **Trabalhos atuais**, selecione o trabalho a ser monitorado. Os detalhes do trabalho são mostrados na caixa de diálogo que aparece à direita.
