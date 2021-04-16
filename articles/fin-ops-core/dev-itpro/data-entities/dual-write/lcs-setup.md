---
title: Configuração da gravação dupla do Lifecycle Services
description: Este tópico explica como configurar uma conexão de gravação dupla do Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e51b4ef1e309e5f89dc82a3776b88c505dc6593d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748532"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configuração da gravação dupla do Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico explica como configurar uma conexão de gravação dupla entre um novo ambiente do Finance and Operations e um novo ambiente do Dataverse a partir do Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Pré-requisitos

Você deve ser um administrador para configurar uma conexão de gravação dupla.

+ Você deve ter acesso ao locatário.
+ Você deve ser um administrador em ambientes de Finance and Operations e ambientes de Dataverse.

## <a name="set-up-a-dual-write-connection"></a>Configurar uma conexão de gravação dupla

Siga essas etapas para configurar a conexão de gravação dupla.

1. Em LCS, vá para seu projeto.
2. Selecione **Configurar** para implantar um novo ambiente.
3. Selecione a versão. 
4. Selecione a topologia. Se houver apenas uma topologia disponível, ela será automaticamente selecionada.
5. Conclua as primeiras etapas do assistente de **Configurações de implantação**.
6. Na guia **Dataverse**, siga uma das etapas a seguir:

    - Se um ambiente do Dataverse já estiver provisionado para o seu locatário, você poderá selecioná-lo.

        1. Defina a opção **Configurar Dataverse** como **Sim**.
        2. Na coluna **Ambientes disponíveis**, selecione o ambiente para integração com os dados de Finance and Operations. A lista inclui todos os ambientes nos quais você tem privilégios administrativos.
        3. Marque a caixa de seleção **Concordar** para indicar que você concorda com os termos e condições.

        ![A guia Dataverse quando um ambiente do Dataverse já estiver provisionado para o seu locatário](../dual-write/media/lcs_setup_1.png)

    - Se o seu locatário ainda não tiver um ambiente do Dataverse, será fornecido um novo ambiente.

        1. Defina a opção **Configurar Dataverse** como **Sim**.
        2. Inserir um nome para o ambiente do Dataverse.
        3. Selecione a região em que o ambiente será implantado.
        4. Selecione o idioma e a moeda padrão para o ambiente.

            > [!NOTE]
            > Não é possível alterar o idioma e a moeda posteriormente.

        5. Marque a caixa de seleção **Concordar** para indicar que você concorda com os termos e condições.

        ![A guia Dataverse quando seu locatário ainda não tiver um ambiente do Dataverse](../dual-write/media/lcs_setup_2.png)

7. Conclua as etapas restantes do assistente de **Configurações de implantação**.
8. Depois que o ambiente tiver um status de **Implantado**, abra a página de detalhes do ambiente. A seção **Integração do Power Platform** mostra os nomes do ambiente Finance and Operations e do ambiente Dataverse vinculado.

    ![Seção Integração do Power Platform](../dual-write/media/lcs_setup_3.png)

9. Um administrador do ambiente Finance and Operations deve efetuar login nas LCS e selecionar **Vincular a CDS para que os aplicativos** concluam o link. A página detalhes do ambiente mostra as informações de contato do administrador.

    Depois que o link for concluído, o status será atualizado para **Vincular ambiente concluído com êxito**.

10. Para abrir o espaço de trabalho **Integração de dados** no ambiente do Finance and Operations e controlar os modelos que estão disponíveis, selecione **Vincular ao CDS para aplicativos**.

    ![Botão Link para o CDS para aplicativos na seção informações sobre a seção Integração do Power Platform](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> Não é possível desvincular ambientes usando o LCS. Para desvincular um ambiente, abra o espaço de trabalho da **Integração de dados** no ambiente do Finance and Operations e selecione **Desvincular**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]