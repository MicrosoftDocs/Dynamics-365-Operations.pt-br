---
title: "Espaço de trabalho móvel disponível em estoque para o aplicativo Microsoft Dynamics 365 for Operations"
description: "O espaço de trabalho móvel disponível em estoque o ajuda a obter informações móveis para estoque reservado e disponível a qualquer hora e em qualquer lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espaço de trabalho móvel disponível em estoque para o aplicativo Microsoft Dynamics 365 for Operations

O espaço de trabalho móvel disponível em estoque o ajuda a obter informações móveis para estoque reservado e disponível a qualquer hora e em qualquer lugar. 

<a name="prerequisites"></a>Pré-requisitos
-------------

| Pré-requisito                                                         | descrição                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Leia sobre a plataforma móvel do Microsoft Dynamics 365 for Operations | [Plataforma móvel do Microsoft Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 for Operations                                          | Um ambiente com a versão 1611 do Microsoft Dynamics 365 for Operations e a atualização 3 da plataforma do Microsoft Dynamics for Operations (novembro de 2016) |
| Hotfix KB 3215650                                                    | Instale o hotfix para habilitar os espaços de trabalho que são fornecidos no Microsoft Dynamics 365 for Operations.                                       |
| Dispositivo móvel com o Dynamics 365 for Operations instalado | Baixe o aplicativo do Dynamics 365 for Operations na sua loja de aplicativos móveis.                                                                           |

## <a name="introduction"></a>Introdução
Geralmente, as empresas têm várias remessas e vários recebimentos de estoque a cada dia. Esses movimentos alteram constantemente o status disponível do estoque. O espaço de trabalho móvel disponível permite ver o status disponível em estoque entre empresas, para que você possa obter as informações mais recentes sobre dados de estoque no dispositivo móvel de sua escolha. Independentemente de trabalhar no depósito, em compras, em vendas, na fabricação, ou no gerenciamento, ou ter outras funções, você pode acessar os dados disponíveis de estoque a qualquer momento e em qualquer lugar. O espaço de trabalho móvel fornece uma exibição instantânea do status disponível através de recursos, e permite exibir o estoque disponível pelas instalações, reservas atuais de materiais e de estoque disponível não reservado. Também é possível inserir números de item para consultar o estoque disponível, e executar uma pesquisa filtrada de produtos ou variantes disponíveis. Especificamente, espaço de trabalho móvel fornece esses recursos:

-   Você pode pesquisar por número ou o nome de produto para encontrar produtos para exibir o status disponível do estoque.
-   Para produtos selecionados, é possível exibir as seguintes informações:
    -   Estoque disponível por site
    -   Estoque disponível por depósito
    -   Estoque disponível por local
    -   Estoque disponível por lote (para produtos controlados por lote)
    -   Estoque disponível por status de estoque

<!-- -->

-   O estoque disponível do produto é mostrado das seguintes maneiras:
    -   Por estoque físico (esta exibição representa o valor total.)
    -   Por reserva física (esta exibição representa o valor reservado.)
    -   Por físico disponível (Esta exibição representa o valor disponível que não tem reservas).

## <a name="get-started"></a>Introdução
Para começar em seu dispositivo móvel:

1.  Na sua loja de aplicativos móveis, baixe e instale o aplicativo do Microsoft Dynamics 365 for operations.
2.  Inicie o aplicativo no seu dispositivo.
3.  Insira sua URL do Dynamics 365.
4.  Insira a empresa à qual deseja se conectar. Por exemplo, insira **USMF**.
5.  No primeiro acesso, são solicitados nome de usuário e senha da sua conta do Microsoft Dynamics 365 for Operations. Insira suas credenciais. Após se conectar, você verá os espaços de trabalho da sua empresa.

Para exibir os espaços de trabalho no seu aplicativo móvel, primeiro você deve publicar os espaços de trabalho desejados para o aplicativo do Dynamics 365 for Operations.

1.  Inicie o Dynamics 365 for Operations.
2.  Vá para **Administração do sistema** &gt; **Configuração** &gt; **Parâmetros do sistema**.
3.  Selecione o **Gerenciar aplicativo móvel**.
4.  Selecione o espaço de trabalho para publicar a plataforma móvel.
5.  Selecione **Publicar espaço de trabalho**.
6.  Atualize seu dispositivo para ver os espaços de trabalho publicados.

## <a name="view-the-onhand-inventory-for-a-product"></a>Exiba o estoque disponível para um produto
1.  No seu dispositivo móvel, selecione o espaço de trabalho **Disponível em estoque**.
2.  Selecione **Verificar estoque disponível de um item**. Você verá uma lista de produtos que estão carregados para seu aplicativo para uso offline. Por padrão, 50 itens são carregados, mas você pode alterar esse número. Para obter mais informações, consulte o manual de pré-leitura.
3.  Se o item não estiver na lista, selecione **Pesquisar mais** para fazer uma pesquisa online no Dynamics 365 for Operations. Pesquise por número de produto ou alterne para uma pesquisa por nome de produto.
4.  Selecione um produto. Se o item tiver uma imagem, ela será mostrada.
5.  Selecione uma das seguintes opções para exibir o status do estoque disponível:
    -   Exibir estoque por site
    -   Exibir estoque disponível por depósito
    -   Exibir estoque disponível por local
    -   Exibir estoque disponível por lote (para produtos controlados por lote)
    -   Exibir estoque disponível por status do estoque

    O estoque disponível do produto é mostrado das seguintes maneiras:
    -   Por estoque físico (esta exibição representa o valor total.)
    -   Por reserva física (esta exibição representa o valor reservado.)
    -   Por físico disponível (Esta exibição representa o valor disponível que não tem reservas).




