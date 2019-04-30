---
title: Postar trabalhos em sites de carreira externos a partir do Attract
description: Este tópico explica como usar o Dynamics 365 for Talent - Attract para postar trabalhos em sites de recrutamento externos.
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
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
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 1653d1e28d02f8a9a4bea8df562ac98d7a350ed1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2019
ms.locfileid: "993659"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a>Postar trabalhos em sites de carreira externos a partir do Attract

[!include [banner](../includes/banner.md)]

Você quer divulgar posições em aberto para o maior número possível de candidatos qualificados. Sites de recrutamento como o Broadbean ajudam a atingir esse objetivo. Agora o Microsoft Dynamics 365 Talent Attract permite postar trabalhos no Broadbean, e a Microsoft está constantemente apresentando novas ofertas nessa área.

## <a name="post-jobs-to-broadbean"></a>Postar trabalhos no Broadbean

Antes de postar trabalhos no Broadbean, você deve configurar a integração dele.

> [!NOTE]
> - Para postar trabalhos em sites externos, você deve ter o [complemento de Contratação abrangente](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Este recurso está atualmente em visualização. Para experimentá-lo, você deve [ativá-lo nas configurações de administrador do Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="configure-broadbean-integration"></a>Configurar a integração do Broadbean

1. Entre no Attract como administrador.
2. Selecione o botão **Configurações** (o símbolo de engrenagem) no canto superior direito da página e selecione **Centro de administração**.
3. Na guia **Configurações do quadro de trabalho**, na seção **Habilitar a integração do Broadbean**, ative a integração.
4. Entre em contato com o Broadbean e insira suas informações em **Nome de Usuário, Cliente, Token de Criptografia**.

> [!WARNING]
> Suas credenciais do Broadbean são confidenciais. Por esse motivo você deve armazená-las e compartilhá-las de forma responsável. Qualquer pessoa que tenha a função Administrador no Attract pode ver essas credenciais.

> [!NOTE]
> A Microsoft e o Attract não estão envolvidos na criação e na manutenção desses valores. É sua responsabilidade mantê-los atualizados no Attract e trabalhar com o Broadbean para resolver quaisquer problemas que envolvam suas credenciais.

### <a name="post-a-job-to-broadbean"></a>Postar um trabalho no Broadbean

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
2. Na seção **Postagens**, selecione o botão de reticências (**…**) que corresponde ao Broadbean e selecione **Exibir**.

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

### <a name="troubleshoot-the-broadbean-integration"></a>Solucionar problemas da integração do Broadbean

Se tiver dificuldade para postar um trabalho no Broadbean, tente executar estas etapas.

1. Verifique se as credenciais do Broadbean que você inseriu no Attract são válidas e estão corretas.
2. Se as credenciais forem válidas e estiverem corretas, entre em contato com o [suporte do Broadbean](https://www.broadbean.com/resources/support/).
3. Se o problema persistir, entre em contato com o [suporte da Microsoft](./talent-support.md).
