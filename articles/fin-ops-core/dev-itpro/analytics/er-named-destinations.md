---
title: Configurar destinos de ER específicos do registro de gerenciamento de impressão
description: Este artigo explica como configurar destinos específicos de registro de gerenciamento de impressão de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.
author: kfend
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.21
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 7c92d580f6adebdba12b7964a42fd4752e9c9205
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285051"
---
# <a name="configure-print-management-record-specific-er-destinations"></a>Configurar destinos de ER específicos do registro de gerenciamento de impressão

[!include [banner](../includes/banner.md)]

Este artigo explica como um usuário que tem a função de Administrador do Sistema ou de Funcionário de Contas a Receber pode executar as seguintes tarefas:

- Configurar destinos denominados [Relatório eletrônico (ER)](general-electronic-reporting.md) para uma solução de ER que gera faturas de texto livre.
- Atribua um destino de ER a um único registro de [gerenciamento de impressão](document-reporting-services.md).

Os procedimentos podem ser concluídos na empresa USMF. Nenhum código é necessário.

## <a name="introduction"></a>Introdução

Você pode configurar [destinos](electronic-reporting-destinations.md) para cada pasta no componente de saída do arquivo de uma [configuração](general-electronic-reporting.md#Configuration) de [formato](general-electronic-reporting.md) de ER que é usado para gerar um documento de saída. Ao executar um formato de ER desse tipo, se você tiver os direitos de acesso apropriados, também poderá alterar as configurações de destino definidas no tempo de execução.

No Microsoft Dynamics 365 Finance **versão 10.0.17 e posterior**, um código de ação pode ser [configurado](er-apis-app10-0-17.md) para um formato de ER para especificar a ação que os usuários executam, ao utilizar esse formato de ER. Por exemplo, no módulo **Contas a receber**, nas configurações de gerenciamento de impressão, você pode selecionar um formato de ER que gera um documento comercial específico, como uma fatura de texto livre. Em seguida, você poderá selecionar **Exibir** para exibir a fatura ou a **Impressão** e enviá-la para uma impressora. Se uma ação for aprovada para o formato de ER em execução no tempo de execução, você poderá [configurar diferentes destinos de ER para diferentes ações do usuário](er-action-dependent-destinations.md).

No Finance **versão 10.0.21 e posterior**, um destino nomeado pode ser [configurado](er-apis-app10-0-21.md) para um formato de ER e atribuído ao registro de gerenciamento de impressão processado quando esse formato ER é executado. Por exemplo, no módulo **Contas a receber**, nas configurações de gerenciamento de impressão, você deseja configurar o registro **Original** para executar as seguintes ações:

- Executar um formato de ER.
- Envie por email a fatura gerada para um cliente.
- Configure o registro de **Cópia** para executar o mesmo formato.
- Imprima uma cópia da fatura para uma impressora de rede.

Nesse caso, você deve configurar destinos de ER diferentes para o formato de ER que está sendo executado e deve selecionar os destinos para diferentes registros de gerenciamento de impressão.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, o recurso **Permitir configurar destinos de ER por item de gerenciamento de impressão** deve estar ativado no espaço de trabalho do [Gerenciamento de recursos](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace). O código-fonte também deve ser alterado para permitir a configuração de destinos de ER denominados na atual instância do Finance habilitar a [nova](er-apis-app10-0-21.md) API do ER.

Além disso, a configuração de ER **Fatura de texto livre (Excel)** deve ser [importada](er-download-configurations-global-repo.md) para sua instância do Finance.

## <a name="configure-a-new-er-destination"></a>Configurar um novo destino de ER

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Selecione uma fatura para a conta do cliente **EUA-001**.
3. Na página **Fatura de texto livre**, na guia **Fatura**, no grupo **Gerenciamento de impressão**, selecione **Gerenciamento de impressão**.
4. Na página **Configuração de gerenciamento de impressão**, expanda **Módulo - Contas a receber** \> **Documentos** \> **Fatura de texto livre**, selecione o registro **Original** e siga estas etapas:

    1.  Observe as configurações atuais do registro selecionado:
        -   O relatório SSRS padrão **FreeTextInvoice.Report** é selecionado no campo **Formato do relatório**.
        -   O nome **\<Default\>** é mostrado no campo **Destino** informando que não há um destino personalizado selecionado para o relatório SSRS atribuído. 
    2.  No campo **Formato do relatório**, selecione a configuração de formato de ER da **Fatura de texto livre (Excel)**.
        -   O nome do campo de **Destino** é alterado para **Nome de destino**.
        -   O nome **\<No named destination\>** é mostrado no campo **Nome de destino** informando que não há um destino nomeado selecionado para o formato de ER atribuído.
    3.  Selecione o botão de seta à direita do campo **Nome de destino**.    
    4. Na página **Destino nomeado como Relatório Eletrônico**, no campo **Nome** digite **Destino principal**.
    5. Selecione **Salvar**.
    6. Na FastTab **Destino do arquivo**, [configure](er-destination-type-email.md) o destino do **Email** para o componente do **Relatório**.
    7. Feche a página **Destino nomeado como Relatório Eletrônico**.
    8. Na página **Configuração de gerenciamento de impressão**, no campo **Nome de destino**, selecione o destino chamado **Destino principal**.

    ![Configurando um destino chamado ER para o formato de ER selecionado e atribuindo-o a um registro de gerenciamento de impressão configurado na página de Configuração de gerenciamento de impressão](./media/er-named-destinations-01.gif)

    Agora você configurou o destino de ER chamado **Destino principal** para o formato **Fatura de texto livre (Excel)** e o atribuiu ao registro de gerenciamento de impressão **Original** em **Módulo - contas a receber** \> **Documentos** \> **Fatura de texto livre**.

5. Expanda **Módulo - contas a receber** \> **Conta - EUA-001** \> **Fatura de texto livre**, selecione o registro **Original** e siga estas etapas:

    1. Selecione e segure (ou clique com o botão direito do mouse) no registro e selecione **Substituir**.
    2. Selecione o botão de seta à direita do campo **Nome de destino**.
    3. Na página **Destino nomeado como Relatório Eletrônico** no Painel de Ações, selecione **Novo**.
    4. No campo **Nome**, digite **Destino EUA-001**.
    5. Na FastTab **Destino do arquivo**, [configure](er-destination-type-print.md) o destino da **Impressora** para o componente **Relatório**.
    6. Feche a página **Destino nomeado como Relatório Eletrônico**.
    7. Na página **Configuração de gerenciamento de impressão**, no campo **Nome de destino**, selecione o destino chamado **Destino EUA-001**.

    ![Configurando um destino chamado ER para o formato de ER selecionado e atribuindo-o a um registro de gerenciamento de impressão configurado na página de Configuração de gerenciamento de impressão](./media/er-named-destinations-02.gif)

    Agora você configurou o destino de ER chamado **Destino EUA-001** para o formato **Fatura de texto livre (Excel)** e o atribuiu ao registro de gerenciamento de impressão **Original** em **Módulo - contas a receber** \> **Conta - US-001** \> **Fatura de texto livre**.

Agora, quando uma fatura de texto livre for processada, o formato de ER **Fatura de texto livre (Excel)** será executado e um dos seguintes eventos ocorrerá:

- Se a fatura de texto livre for para um cliente que não seja EUA-001, o documento gerado será enviado por email.
- Se a fatura de texto livre for para um cliente que não seja EUA-001, o documento gerado será impresso.

> [!NOTE]
> Quando um destino nomeado não é definido para um registro de gerenciamento de impressão processado no tempo de execução, os destinos padrão de ER são usados se estiverem disponíveis para o formato ER que está sendo executado.

> [!IMPORTANT]
> Na página **Destino de relatório eletrônico** (**Administração da organização** \> **Relatório eletrônico** \> **Destino de relatório eletrônico**), se você selecionar um formato de ER para o qual pelo menos um destino nomeado foi configurado, você será notificado sobre a presença de destinos nomeados.
>
> ![Notificação sobre a existência de destinos nomeados configurados para o formato de ER selecionado na página destino do relatório eletrônico](./media/er-named-destinations-03.png)
>
> Se você excluir o destino padrão, todos os destinos nomeados também serão excluídos. Se os destinos nomeados foram selecionados para registros de gerenciamento de impressão, a seleção desses destinos nomeados será cancelada.

## <a name="copy-an-existing-er-destination-as-a-new-named-destination"></a>Copiar um destino de ER existente como um novo destino nomeado

Quando o destino de ER padrão está disponível para um formato de ER, ele pode ser usado como um modelo para novos destinos de ER. Para criar um novo destino de ER com base no destino padrão, selecione **Copiar do padrão** na página **Destino nomeado como Relatório Eletrônico**. O novo destino é nomeado **Padrão**. Você pode repetir essa etapa quantas vezes forem necessárias.

Você pode selecionar qualquer destino nomeado existente como um modelo para um novo destino nomeado. Para criar um novo destino de ER nomeado com base no destino nomeado selecionado, selecione **Copiar** na página **Destino nomeado como Relatório Eletrônico**. O novo destino tem o mesmo nome que o destino nomeado selecionado, mas o sufixo "Cópia" é adicionado. Você pode repetir essa etapa quantas vezes forem necessárias.

## <a name="security-considerations"></a>Considerações de segurança

Você pode configurar destinos de ER denominados na página **Configuração do gerenciamento de impressão** somente se tiver [permissão](../sysadmin/role-based-security.md#permissions) para executar essa tarefa. A permissão pode ser concedida a você se o [direito](../sysadmin/role-based-security.md#duties) **Configurar destino de formato de relatório eletrônico** for atribuído a um de suas [funções de segurança](../sysadmin/role-based-security.md#security-roles). Para obter mais informações, consulte [Considerações de segurança](electronic-reporting-destinations.md#security-considerations).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório Eletrônico (ER)](general-electronic-reporting.md)

[Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)

[Alterações na API da estrutura do relatório eletrônico para Application update 10.0.17](er-apis-app10-0-17.md)

[Alterações na API da estrutura do relatório eletrônico para Application update 10.0.21](er-apis-app10-0-21.md)

[Alterar código para permitir que os usuários configurem e usem destinos nomeados de ER](er-api-named-destinations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
