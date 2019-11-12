---
title: Lançar trabalhos de sites de carreira externos a partir do Attract
description: 'Este tópico explica como usar o Dynamics 365 Talent: Attract para postar trabalhos em sites de recrutamento externos.'
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 2c822a1f799144bb9240fc0cbdeb6c5441e278af
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551394"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a>Lançar trabalhos de sites de carreira externos a partir do Attract

[!include [banner](../includes/banner.md)]

O Microsoft Dynamics 365 Talent: Attract ajuda a obter o talento que você precisa, permitindo que você lance seus trabalhos diretamente do Attract para o Broadbean. Depois de [criar um trabalho](./creating-jobs-attract.md), tudo que você tem a fazer é clicar em um botão para começar seu trabalho antes de todos os possíveis candidatos ao trabalho no Broadbean.

O lançamento de trabalhos no Broadbean requer uma licença de Broadbean apropriada. A Broadbean oferece vários produtos e planos. Para obter mais informações sobre licença e preço, [contate o Broadbean](https://www.broadbean.com/contact-us/).

Se você for um administrador e precisar de mais informações sobre como configurar a integração do Broadbean com o Attract, consulte [Inserir configurações para quadros de trabalho externos](./attract-admin-job-board-settings.md).

## <a name="post-jobs-to-broadbean"></a>Lançar trabalhos no Broadbean

Depois que o Broadbean é ativado, os recrutadores e administradores podem postar trabalhos nele. Você deve ter uma URL de solicitação do trabalho.

1. No Attract, abra o trabalho que você quer postar no Broadbean.
2. Na seção **Postagens**, selecione o botão **Lançar Agora** que corresponde ao Broadbean.
3. Siga as instruções na janela do Broadbean.

O Attract passa as seguintes informações para o Broadbean:

- ID da solicitação
- Cargo
- Descrição de trabalho
- Local de trabalho
- URL de solicitação
- Informações do recrutador

Depois que o Broadbean conclui a postagem com êxito, a seção **Postagens** do trabalho no Attract mostra o status do Broadbean como **Enviado**.

> [!NOTE]
> - O preenchimento do campo **Indústria** é obrigatório no Broadbean. No momento, esse campo é definido como **Tecnologia da Informação** por padrão. Entretanto, você pode alterar o valor para a indústria correta na janela da postagem de trabalho do Broadbean.
> - O Broadbean precisa de algum tempo para concluir a postagem do trabalho em todos os quadros de trabalho selecionados por você. Por isso pode haver um pequeno atraso para que o Attract possa mostrar uma atualização do status do trabalho.

### <a name="view-a-broadbean-job-posting"></a>Exibir uma postagem de trabalho do Broadbean

Depois de postar um trabalho no Broadbean, você pode exibi-lo no Attract.

1. No Attract, abra o trabalho que você quer exibir no Broadbean.
2. Na guia **Lançamentos**, selecione o botão de reticências (**...**) que corresponde ao Broadbean e, em seguida, selecione **Exibir**.

A postagem de trabalho do Broadbean aparece em uma nova janela.

### <a name="update-a-broadbean-job-posting"></a>Atualizar uma postagem de trabalho do Broadbean

Você pode atualizar uma postagem de trabalho do Broadbean de duas formas.

1. No Attract, abra o trabalho que você quer atualizar.
2. Na seção **Postagens**, selecione o botão **Atualizar Postagem** que corresponde ao Broadbean.
3. Edite a postagem na janela do Broadbean.

–ou–

1. No Attract, abra o trabalho que você quer exibir no Broadbean.
2. Na seção **Postagens**, selecione o botão de reticências (**…**) que corresponde ao Broadbean e selecione **Exibir**.
3. Na janela do Broadbean, edite os detalhes do trabalho e repita a postagem. Os detalhes do trabalho no Attract não são modificados.

### <a name="remove-a-broadbean-job-posting"></a>Remover uma postagem de trabalho do Broadbean

Você pode remover uma postagem de trabalho do Broadbean conforme necessário.

1. No Attract, abra o trabalho que você quer remover.
2. Na seção **Postagens**, selecione o botão de reticências (**…**) que corresponde ao Broadbean e selecione **Remover Lançamento**.

Depois que o Broadbean remove o trabalho, o item do Broadbean no Attract tem um botão **Lançar Agora**. A presença desse botão indica que o trabalho foi removido e pode ser postado novamente.

### <a name="troubleshoot-job-posting-to-broadbean"></a>Solucionar problemas de lançamento de trabalhos no Broadbean

Se tiver dificuldade para postar um trabalho no Broadbean, tente executar estas etapas.

1. Verifique se as credenciais do Broadbean que você inseriu no Attract são válidas e estão corretas.
2. Se as credenciais forem válidas e estiverem corretas, entre em contato com o [suporte do Broadbean](https://www.broadbean.com/resources/support/).
3. Se o problema persistir, entre em contato com o [suporte da Microsoft](./talent-support.md).

## <a name="see-also"></a>Consulte também

[Criar trabalhos](./creating-jobs-attract.md)

[Inserir configurações para quadros de trabalhos externos](./attract-admin-job-board-settings.md)
