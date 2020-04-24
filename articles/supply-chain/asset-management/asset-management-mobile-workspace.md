---
title: Espaço de trabalho móvel Gerenciamento de ativos
description: Este tópico fornece informações sobre o espaço de trabalho móvel Gerenciamento de ativos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: 525f21d076027f1bf339e59fd0e346706044839c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216496"
---
# <a name="asset-management-mobile-workspace"></a>Espaço de trabalho móvel Gerenciamento de ativos

[!include [banner](../../includes/banner.md)]


Este tópico fornece informações sobre o espaço de trabalho móvel Gerenciamento de ativos. Este espaço de trabalho permite aos usuários visualizar e criar solicitações de manutenção e ordens de serviço. Os usuários também podem visualizar os trabalhos de ordens de serviço atribuídos em uma exibição de calendário ou de lista. Os ativos e os locais funcionais também podem ser visualizados e pesquisados.


## <a name="overview"></a>Visão Geral

O Gerenciamento de Ativos é um módulo avançado para gerenciar ativos e trabalhos de ordens de serviço no Dynamics 365 Supply Chain Management. O espaço de trabalho móvel **Gerenciamento de ativos** permite que os usuários vejam rapidamente os trabalhos de ordens de serviço atribuídos no dispositivo móvel de sua escolha. Os usuários também podem criar e gerenciar solicitações de manutenção, atualizar o estado de ciclo de vida e visualizar detalhes do ativo e local funcional usando o dispositivo móvel.

Especificamente, o espaço de trabalho móvel **Gerenciamento de ativos** permite que os usuários executem estas tarefas:

- Criar, exibir e editar solicitações de manutenção, tirar uma foto ou anexar uma imagem existente à solicitação de manutenção, alterar o estado de ciclo de vida da solicitação de manutenção. 
- Criar, exibir e editar ordens de serviço, tirar uma foto ou anexar uma imagem existente à ordem de serviço, alterar o estado de ciclo de vida da ordem de serviço, exibir trabalhos de ordens de serviço.
- Exibir trabalhos de ordens de serviço atribuídos em uma exibição de calendário.
- Criar, exibir e editar o trabalho da ordem de serviço, atualizar contadores de ativos, exibir lista de verificação de manutenção, exibir e editar notas de trabalho da ordem de serviço, exibir as ferramentas necessárias para o trabalho da ordem de serviço.
- Exibir ou procurar um ativo ou local funcional específico.


## <a name="prerequisites"></a>Pré-requisitos

Os pré-requisitos variam conforme a versão do Dynamics 365 Supply Chain Management implantada na organização.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-supply-chain-management"></a>Pré-requisitos se você usa o Microsoft Dynamics 365 Supply Chain Management 
Se o Microsoft Dynamics 365 Supply Chain Management foi implantado na organização, o administrador do sistema deve publicar o espaço de trabalho móvel **Gerenciamento de ativos**. Para obter instruções, consulte [Publicar um espaço de trabalho móvel](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

## <a name="download-and-install-the-mobile-app"></a>Baixa e instala o aplicativo móvel.
Baixa e instala o aplicativo móvel Dynamics 365 for Unified Operations:

- [Para telefones Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Entrar no aplicativo móvel
1. Inicie o aplicativo móvel no seu dispositivo.

2. Insira sua URL do Dynamics 365.

3. Na primeira vez que você iniciar a sessão, será solicitado o nome de usuário e a senha. Insira suas credenciais.

4. Depois de entrar, serão exibidos os espaços de trabalho disponíveis da sua empresa. Observe que se o administrador do sistema publicar um novo espaço depois, você terá de atualizar a lista dos espaços de trabalho móveis.

![Figura 1](media/am-mobile-01.png)


## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>Exibir trabalhos de ordens de serviço atribuídos na exibição de calendário

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.

2. Selecione **Meu calendário de trabalhos de ordens de serviço**.

3. Selecione a data cujos trabalhos de ordens de serviço você deseja exibir. Na lista, você verá a ID do ativo e a ID do local funcional para cada trabalho da ordem de serviço.

4. Selecione um trabalho da ordem de serviço na lista para ver os detalhes do trabalho: detalhes do ativo e local funcional, além de outros links de navegação para exibir **Anexos**, **Listas de verificação**, **Ferramentas**, **Contadores de ativos**, **Notas**, **Diários**.

![Figura 2](media/am-mobile-02.png)


## <a name="create-a-work-order-job"></a>Criar um trabalho da ordem de serviço

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.

2. Selecione **Todas as ordens de serviço de manutenção**.

3. Selecione a ordem de serviço para a qual você deseja criar um novo trabalho.

4. Selecione o botão **Adicionar linha**.

5. Selecione o **Ativo** para o qual você deseja criar um novo trabalho da ordem de serviço.

6. Selecione **Tipo de trabalho de manutenção**, **Variação do tipo de trabalho de manutenção** e **Ofício**.

7. Selecione **Concluído**.

![Figura 3](media/am-mobile-03.png)


## <a name="add-attachment-to-a-work-order-job"></a>Adicionar anexos a um trabalho da ordem de serviço

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.

2. Selecione **Todas as ordens de serviço de manutenção**.

3. Selecione a ordem de serviço > trabalho da ordem de serviço ao qual você deseja adicionar um anexo.
    - Como opção, você também pode selecionar **Meu calendário de trabalhos de ordens de serviço** ou **Minha lista de trabalhos de ordens de serviço** na home page para navegar até a página **Detalhes do trabalho da ordem de serviço**.

4. Selecione **Anexos** na página **Detalhes da ordem de serviço**.

5. Você verá os anexos existentes no trabalho da ordem de serviço. Selecione **Adicionar anexo**.

6. Insira o **Nome** e as **Notas** do anexo.

7. Selecione **Escolher imagem** para selecionar uma foto na galeria do dispositivo móvel ou **Tirar foto** para tirar uma foto.

8. Selecione **Concluído**.

![Figura 4](media/am-mobile-04.png)


## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Exibir a lista de verificação de manutenção em um trabalho da ordem de serviço

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.

2. Selecione **Todas as ordens de serviço de manutenção**.

3. Selecione a ordem de serviço > trabalho da ordem de serviço cujas listas de verificação você deseja exibir.
    - Como opção, você também pode selecionar **Meu calendário de trabalhos de ordens de serviço** ou **Minha lista de trabalhos de ordens de serviço** na home page para navegar até a página **Detalhes do trabalho da ordem de serviço**.

4. Selecione **Listas de verificação** na página **Detalhes do trabalho da ordem de serviço**.

5. Você verá uma lista de linhas da lista de verificação relacionadas ao trabalho da ordem de serviço. Selecione uma linha de lista de verificação para exibir **Instruções** e adicionar **Notas**.

6. Selecione o botão Voltar (**<**) para retornar à página anterior.

![Figura 5](media/am-mobile-05.png)


## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>Exibir e atualizar contadores de ativos em um trabalho da ordem de serviço

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.

2. Selecione **Todas as ordens de serviço de manutenção**.

3. Selecione a ordem de serviço > trabalho da ordem de serviço cujos contadores de ativos você deseja exibir.
    - Como opção, você também pode selecionar **Meu calendário de trabalhos de ordens de serviço** ou **Minha lista de trabalhos de ordens de serviço** na home page para navegar até a página **Detalhes do trabalho da ordem de serviço**.

4. Selecione **Contadores de ativos** na página **Detalhes do trabalho da ordem de serviço**.

5. Você verá uma lista de contadores de ativos relacionadas ao trabalho da ordem de serviço. Selecionar o ícone de lápis em uma linha de contador de ativos para atualizar o valor do contador.

6. Insira um novo valor de contador e selecione **Concluído**.

![Figura 6](media/am-mobile-06.png)


## <a name="register-consumption-on-a-work-order-job"></a>Registrar o consumo em um trabalho da ordem de serviço

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.

2. Selecione **Todas as ordens de serviço de manutenção**.

3. Selecione a ordem de serviço > trabalho da ordem de serviço ao qual você deseja adicionar registros de consumo.
    - Como opção, você também pode selecionar **Meu calendário de trabalhos de ordens de serviço** ou **Minha lista de trabalhos de ordens de serviço** na home page para navegar até a página **Detalhes do trabalho da ordem de serviço**.

4. Selecione **Diários** na página **Detalhes do trabalho da ordem de serviço**.

5. Selecione **Adicionar horas** para criar registros de horas de trabalho.
    1. Selecione a **Categoria** na pesquisa.
    2. No campo **Horas** , insira o número de horas de trabalho gastas no trabalho da ordem de serviço.
    3. Selecione a **Propriedade da linha** apropriada.
    4. Selecione **Concluído**.

6. Selecione **Adicionar itens** para criar registros de itens.
    1. Selecione o **Número do item** na pesquisa.
    2. Selecione o **Site** na pesquisa.
    3. Insira a **Quantidade** de itens consumidos.
    4. Selecione **Concluído**.

7. Selecione **Adicionar despesa** para criar registros de despesas.
    1. Selecione a **Categoria** na pesquisa.
    2. Insira a quantidade do registro de despesas.
    3. Selecione a **Moeda de venda** na pesquisa.
    4. Insira o **Preço de custo** do registro da despesa.
    5. Selecione **Concluído**.

![Figura 7](media/am-mobile-07.png)


## <a name="update-lifecycle-state-on-a-work-order"></a>Atualizar o estado de ciclo de vida em uma ordem de serviço

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.

2. Selecione **Todas as ordens de serviço de manutenção**.

3. Selecione a ordem de serviço cujo estado de ciclo de vida você deseja atualizar.

4. Selecione o botão **Atualizar estado** na parte inferior da tela.

5. Selecione um novo estado de ciclo de vida na lista.

6. Selecione **Concluído**.

![Figura 8](media/am-mobile-08.png)


## <a name="create-a-maintenance-request"></a>Criar uma solicitação de manutenção

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.

2. Selecione **Todas as solicitações de manutenção**.

3. Selecione **Ações** na parte inferior da tela e selecione **Criar solicitação de manutenção**.

4. Se a sequência numérica estiver habilitada para solicitações de manutenção em **Gerenciamento de ativos**, o campo **Solicitação de manutenção** ficará oculto porque ele será preenchido automaticamente. Se o campo **Solicitação de manutenção** estiver visível, insira uma ID da solicitação de manutenção.

5. Selecione um **Tipo de solicitação de manutenção**.

6. Insira uma **Descrição** para a solicitação de manutenção.

7. Selecione o **Ativo** para o qual você deseja criar a solicitação.

8. Selecione o **Nível de serviço** da solicitação de manutenção.

9. Selecione **Concluído**.

![Figura 9](media/am-mobile-09.png)


## <a name="add-attachment-to-a-maintenance-request"></a>Adicionar anexos a uma solicitação de manutenção

1. No seu dispositivo móvel, abra o espaço de trabalho **Gerenciamento de ativos**.

2. Selecione **Todas as solicitações de manutenção**.

3. Selecione a solicitação de manutenção à qual você deseja adicionar um anexo.

4. Selecione **Anexos** na parte inferior da tela.

5. Selecione **Adicionar anexos**.

6. Insira o **Nome** e as **Notas** do anexo.

7. Selecione **Escolher imagem** para selecionar uma foto na galeria do dispositivo móvel ou **Tirar foto** para tirar uma foto.

8. Selecione **Concluído**.

![Figura 10](media/am-mobile-10.png)

