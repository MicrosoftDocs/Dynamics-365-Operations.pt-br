---
title: Criar e enviar um guia de integração usando o Dynamics 365 Talent - Onboard
description: Este tópico explica como usar o aplicativo Microsoft Dynamics 365 Talent - Onboard para criar um guia de integração para suas novas contratações. Esta tarefa é uma etapa inicial essencial em uma estratégia de contratação até a demissão do gerenciamento de capital humano (HCM).
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2371d86165390503312c2848842acf4745a8ed7a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460306"
---
# <a name="create-and-send-an-onboarding-guide"></a>Criar e enviar uma guia de integração

[!include [banner](includes/banner.md)]

O Microsoft Dynamics 365 Talent: Onboard permite criar guias de integração por meio de modelos que você mesmo criou, de modelos disponíveis em uma galeria ou do zero.

Após criar um guia de integração, você pode enviá-lo para uma nova contratação. Como alternativa, você pode enviá-lo a várias novas contratações especificadas em um arquivo do Microsoft Excel que você baixa do aplicativo Onboard.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a>Criar um guia de integração por meio de um modelo e enviá-lo para uma única nova contratação

1. No menu esquerdo, selecione **Modelos**.
2. Em **Meus modelos**, selecione o modelo que deseja configurar como um guia de integração para a nova contratação.
3. Edite o modelo como desejar. Lembre-se de salvar seu trabalho conforme progredir.
4. Quando concluir a edição do modelo, selecione **Criar guia**.

    [![Criar um guia de integração por meio de um modelo](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)

5. Na janela **Criar um guia**, em **Quem você está integrando**, insira o nome ou o endereço de email da nova contratação. Se a nova contratação ainda não estiver no sistema, selecione **Adicionar agora** e insira as informações do funcionário.

    ![[Inserindo informações para o guia de integração](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. Em **Quando elas começam**, selecione uma data inicial.
7. Caso o guia de integração precise ser enviado automaticamente à nova contratação em uma data específica, certifique-se de ativar a opção **Agendar uma data de envio automático** e selecione a data de envio automático. Para enviar o guia imediatamente, desative a opção **Agendar uma data de envio automático**.
8. Selecione **Concluído**.
9. Quando terminar de editar o guia de integração, selecione **Enviar** no canto superior direito. E então, siga uma destas etapas:

    - Para enviar um link do guia de integração para a nova contratação, selecione **Copiar link** e então **Copiar**.
    - Para personalizar o email do guia de integração antes de enviar, selecione **Personalizar o email antes de enviar**, selecione **Avançar**, personalize o email como preferir e selecione **Enviar**.
    - Para enviar o email sem personalização, selecione **Avançar** e **Enviar**.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a>Criar um guia de integração por meio de um modelo e enviá-lo para várias novas contratações

O Onboard permite enviar um guia de integração simultaneamente para várias novas contratações.

1. No menu esquerdo, selecione **Modelos**.
2. Em **Meus modelos**, selecione o modelo que deseja configurar como um guia de integração para as novas contratações.
3. Edite o modelo como desejar. Lembre-se de salvar seu trabalho conforme progredir.
4. Quando concluir a edição do modelo, selecione **Criar guia**.
5. Na janela **Criar guia**, selecione **Precisa fazer a integração de mais de uma pessoa por vez**.

    [![Criar um guia de integração para várias novas contratações](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)

6. Selecione **Modelo de nova contratação**.
7. Após baixar o arquivo .xlsx, selecione **Abrir**, insira as informações dos funcionários na pasta de trabalho do Excel e salve a pasta de trabalho.

    [![Baixar o modelo do Excel para enviar o guia de integração para várias novas contratações](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)

    > [!NOTE]
    > Para poder editar a pasta de trabalho, é necessário selecionar **Habilitar edição** no Excel.
    > 
    > [![Habilitar edição](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)

8. Arraste a pasta de trabalho do Excel para a área designada na janela **Criar vários guias**, ou clique em qualquer lugar nessa área para procurar o arquivo no seu computador.

    [![Arrastar a pasta de trabalho editada](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)

9. Quando terminar de editar o guia de integração, selecione **Enviar** no canto superior direito. E então, siga uma destas etapas:

    - Para enviar um link do guia de integração para as novas contratações, selecione **Copiar link** e então **Copiar**.
    - Para personalizar o email do guia de integração antes de enviar, selecione **Personalizar o email antes de enviar**, selecione **Avançar**, personalize o email como preferir e selecione **Enviar**.
    - Para enviar o email sem personalização, selecione **Avançar** e **Enviar**.

## <a name="create-a-guide-without-using-a-template"></a>Criar um guia sem usar um modelo

Você não precisa sempre criar um guia por meio de um modelo. Em vez disso, se preferir, você pode criar um guia do zero.

1. No menu esquerdo, selecione **Guias** e selecione o botão **Adicionar** (o sinal de adição \[**+**\]).
2. Na janela **Criar um guia**, em **Quem você está integrando**, insira o nome ou o endereço de email da nova contratação. Se a nova contratação ainda não estiver no sistema, selecione **Adicionar agora** e insira as informações do funcionário.

    ![[Inserindo informações para o guia de integração](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. Em **Quando elas começam**, selecione uma data inicial.
4. Caso o guia de integração precise ser enviado automaticamente à nova contratação em uma data específica, certifique-se de ativar a opção **Agendar uma data de envio automático** e selecione a data de envio automático. Para enviar o guia imediatamente, desative a opção **Agendar uma data de envio automático**.
5. Selecione **Concluído**.

## <a name="save-a-guide-as-a-template"></a>Salvar um guia como modelo

Você pode salvar um guia de integração como modelo. Dessa forma, você poderá poupar tempo quando você precisar criar mais guias de integração posteriormente.

1. No menu esquerdo, selecione **Guias**.
2. Selecione o botão **Mais** (as reticências \[**...**\]) no guia que deseja usar para criar um modelo e, em seguida, selecione **Salvar como modelo**.

    ![[Salvando um guia de integração como um modelo](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. Na janela **Salvar como um novo modelo**, digite um nome para o novo modelo e selecione **Salvar**.

## <a name="next-steps"></a>Próximas etapas

- [Editar guias e modelos de integração](./onboard-edit-guides-templates.md)
- [Compartilhar conteúdo com outros contribuintes](./onboard-share-template.md)
- [Exibir o status de tarefas e da integração de funcionários](./onboard-view-status.md)
- [Criar equipes de contratação no Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Consulte também

- [Experimentar ou comprar o Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Novidades ou alterações no Dynamics 365 Talent](./whats-new.md)
- [Planos de versão](https://docs.microsoft.com/business-applications-release-notes/index)
- [Obter suporte para o Microsoft Dynamics 365 Talent](./talent-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]