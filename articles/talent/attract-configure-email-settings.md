---
title: Definir as configurações de email no Attract
description: Este tópico explica como definir as configurações dos emails enviados pelo Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: e641e3f0d1873d91be1a1dc9bc22eb734a2b21d5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460299"
---
# <a name="configure-email-settings-in-attract"></a>Definir as configurações de email no Attract

[!include [banner](includes/banner.md)]

Sua marca estabelece confiança e ajuda você a construir um relacionamento com candidatos antes de se candidatarem às suas posições. A percepção positiva da marca atrai os maiores talentos e aumenta a fidelidade dos funcionários existentes. O Microsoft Dynamics 365 Talent: Attract permite que você configure emails para que reflitam a marca da sua empresa. Portanto, você pode fornecer uma experiência consistente a candidatos ao trabalho à medida que avancem no processo de solicitação de emprego.

O Attract permite que você execute estas ações:

- Defina configurações de email para que a conta de serviço de email do Microsoft Exchange da sua empresa seja usada. Assim, os candidatos sabem que os emails vêm da sua empresa. Por exemplo, você pode definir suas configurações para que os candidatos recebam email do `recruiting@contoso.com` em vez do `contoso@microsoft.com`.
- Crie marcas consistentes para todas as suas comunicações por email, definindo um cabeçalho e rodapé globais para os modelos de email. 

> [!NOTE]
> Para configurar o Attract de forma que ele utilize a conta de serviço de email da sua empresa para enviar emails, você precisa do complemento de contratação abrangente.

## <a name="connect-an-email-service-account"></a>Conecte uma conta de serviço de email

Ao conectar a conta de serviço de email da sua empresa, você pode criar uma experiência de email de marca para os candidatos ao trabalho. Se você não conectar a conta da sua empresa, o Attract utilizará a conta de serviço de email padrão com a marca da Microsoft.

1. Selecione **Configurações** (o símbolo de engrenagem no canto superior direito) e selecione **Centro de administração**.
2. Na guia **Configurações de email**, em **Contas do serviço de email**, selecione **Conectar-se a uma conta de empresa**.

    ![Como conectar a conta de serviço de email da sua empresa no Attract](./media/attract-admin-email-service-accounts.png)

    Para obter mais informações sobre como criar uma conta de email compartilhada, consulte [Caixas de correio compartilhadas em Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).

3. Na janela de entrada da Microsoft, entre usando suas credenciais corporativas.
4. Se você ainda não tiver configurado uma conta de serviço de email ou se desejar adicionar uma nova conta, selecione **Adicionar nova conta de serviço** e insira as informações de seu email. Se você já configurou a conta de serviço de email que deseja usar, selecione-a.

Quando sua conta de serviço de email for configurada com êxito, você a verá listada em **Contas de serviço de email**.

## <a name="disconnect-an-email-service-account"></a>Desconecte uma conta de serviço de email

Se desejar parar de usar o domínio da empresa em comunicações por email por meio do Attract, você poderá desconectar uma conta de serviço de email.

1. Selecione **Configurações** (o símbolo de engrenagem no canto superior direito) e selecione **Centro de administração**.
2. Na guia **Configurações de email**, em **Contas do serviço de email**, selecione o botão **Mais** (três pontos verticais) ao lado da conta de serviço de email a ser desconectada.
3. Selecione **Desconectar a conta de email**.

    ![Como desconectar a conta de serviço de email da sua empresa](./media/attract-admin-disconnect-email-account.png)

4. Quando for solicitado a confirmar a operação, selecione **Desconectar**.

    ![Confirmando a desconexão da conta de serviço de email da sua empresa](./media/attract-admin-email-confirm-disconnect.png)

Se você não conectar uma conta de serviço de email diferente, os emails enviados do Attract usarão a conta de serviço de email padrão com a marca da Microsoft.

## <a name="configure-email-template-settings"></a>Defina configurações de modelo de email

Você pode carregar uma imagem do logotipo da sua empresa e outras informações como um cabeçalho com marca para seus emails. Você também pode fornecer links para sua política de privacidade e termos de uso em rodapés de email.

> [!NOTE]
> Você deve estar em conformidade com todas as leis aplicáveis de seu país ou região e também com o país ou região que rege o destinatário do email. Essas leis incluem regulamentações antispam.

1. Selecione **Configurações** (o símbolo de engrenagem no canto superior direito) e selecione **Centro de administração**.
2. Na guia **Configurações de email**, em **Configurações de modelo de email**, arraste a imagem que você deseja usar como o cabeçalho do email até a caixa de imagem ou clique na caixa de imagem para procurar o arquivo. Para substituir uma imagem existente, primeiro selecione **Remover** ao lado dela. A imagem pode ser um arquivo JPEG JPG, PNG ou SVG. É recomendável que as imagens tenham entre 25 e 800 pixels de largura e entre 25 e 150 pixels de altura. O tamanho máximo do arquivo para o cabeçalho é de 1 megabyte (MB).

    ![Como adicionar uma imagem ao cabeçalho de email da sua empresa](./media/attract-admin-email-header.png)

3. Em **Sua política de privacidade para comunicações**, forneça um link para a política de privacidade da sua empresa. Em **Seus termos e condições para comunicações**, forneça um link para os termos de uso da sua empresa.

    ![Como adicionar links para a política de privacidade e os termos de uso da sua empresa para o rodapé de email](./media/attract-admin-email-footer.png)

4. Selecione **Salvar** para salvar as suas configurações de modelo de email.


[!INCLUDE[footer-include](../includes/footer-banner.md)]