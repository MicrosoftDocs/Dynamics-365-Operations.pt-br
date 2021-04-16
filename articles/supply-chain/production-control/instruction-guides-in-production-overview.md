---
title: Fornecer guias de realidade combinada para trabalhadores na produção
description: Este tópico explica como integrar o módulo de gerenciamento de produção no Microsoft Dynamics 365 Supply Chain Management ao Dynamics 365 Guides.
author: cabeln
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 59fe3996013737198d4fbc86d64f8ef9dbe035e4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829345"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a>Fornecer guias de realidade combinada para trabalhadores na produção

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Os trabalhadores em processos de produção se beneficiarão das instruções relevantes fornecidas no momento certo no contexto do seu trabalho. As *instruções* se aplicam a vários domínios de trabalho, incluindo: montagem, serviço, operações, certificação e segurança. Em todas essas principais funções de negócios, as instruções de treinamento contínuo podem ajudar a capacitar os trabalhadores a produzir mais e a trabalhar melhor.

## <a name="introduction"></a>Introdução

Você pode fornecer instruções de maneiras diferentes. Um sistema eficiente que faz envios pronto para uso usa o [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).

O Dynamics 365 Guides pode ajudar a capacitar seus funcionários com aprendizado prático. Você pode definir processos padronizados com instruções passo a passo que orientam seus funcionários para as ferramentas e peças necessárias e mostram aos funcionários como usar essas ferramentas em situações reais de trabalho.

Você pode anexar guias a vários aspectos do controle de produção, incluindo:

- [Recursos](#resources)
- [Grupos de recursos](#resource-groups)
- [Produtos liberados](#released-products)
- [Fórmulas](#formulas)
- [Versões da fórmula](#formula-versions)
- [Listas de materiais (BOMs)](#bom)
- [Versões da BOM](#bom-versions)
- [Roteiros](#routes)
- [Versões de roteiro](#route-versions)
- [Relações de operação de roteiro](#route-operation-relations)

> [!NOTE]
> Você também pode anexar guias com o gerenciamento de ativos. Para obter mais informações sobre essa opção consulte [Integrar o Dynamics 365 Supply Chain Management (gerenciamento de ativos) ao Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).

Quando um trabalhador de linha de frente escolhe um trabalho no chão de fábrica por meio do Supply Chain Management, ele pode ver [os guias relevantes](#logic) no cartão de trabalho. Quando o trabalhador escolhe um guia específico, um código QR para esse guia é mostrado na tela. O trabalhador usa o HoloLens para digitalizar o código QR, que inicia os guias e mostra as instruções necessárias.

As subseções a seguir descrevem alguns cenários selecionados nos quais as empresas em vários setores podem obter o maior valor ao usar guias para apresentar instruções de manufatura.

### <a name="assembly"></a>Montagem

![Usar guias em tarefas de montagem](media/instruction-guides-hero-assembly.png "Usar guias em tarefas de serviço")

As instruções nas operações de montagem mostram aos trabalhadores as ferramentas e as peças necessárias e como usá-las em situações reais de trabalho.

Os gerentes de produção podem criar e atribuir guias, por exemplo, para [roteiros de produção](routes-operations.md), [relações de operação](routes-operations.md#operation-relations) ou [listas de materiais](bill-of-material-bom.md). Os trabalhadores encontrarão as instruções relevantes sobre a respectiva experiência operacional no chão de fábrica.

### <a name="service"></a>Serviço

![Usar guias em tarefas de serviço](media/instruction-guides-hero-service.png "Usar guias em tarefas de serviço")

Capacite técnicos com instruções guiadas no local do trabalho, eliminando a necessidade de programar visitas adicionais.

Os gerentes de serviço podem atribuir guias, por exemplo, a [produtos específicos](../../commerce/product.md) que passam por rotinas de avaliação de qualidade.

### <a name="quality"></a>Qualidade

![Usar guias em tarefas de controle de qualidade](media/instruction-guides-hero-quality.png "Usar guias em tarefas de controle de qualidade")

Implemente novos processos e garanta maior consistência ao transformar o conhecimento dos funcionários em uma ferramenta repetível.

Os gerentes de controle de qualidade podem atribuir os guias, por exemplo, a [produtos específicos](../../commerce/product.md) que passam por rotinas de avaliação de qualidade.

### <a name="certifications"></a>Certificações

![Usar guias para tarefas relacionadas à certificação](media/instruction-guides-hero-certification.png "Usar guias para tarefas relacionadas à certificação")

Certifique-se de que cada funcionário atenda a altos padrões, identificando rapidamente quem precisa de ajuda e onde.

### <a name="safety"></a>Segurança

![Usar guias nas instruções de segurança do trabalho](media/instruction-guides-hero-safety.png "Usar guias nas instruções de segurança do trabalho")

Forneça instruções que orientem sobre procedimentos perigosos virtualmente antes de tentativas no ambiente físico. Com uma abordagem de realidade misturada, os funcionários podem experimentar procedimentos perigosos virtualmente.

Os gerentes de produção podem fornecer instruções de manuseio dedicadas para procedimentos de manuseio de material tóxico ou de manuseio delicado, atribuindo instruções a [itens de produção](../../commerce/product.md), [roteiros](routes-operations.md) e [operações](routes-operations.md#operation-relations).

## <a name="get-started-with-instructions-and-guides"></a>Introdução a instruções e guias

Para habilitar as instruções em processos de produção, o Supply Chain Management oferece uma integração pronta para uso com o Dynamics 365 Guides. Uma instância do aplicativo licenciada e instalada do Guides é necessária para criar, manter e atribuir instruções de realidade misturada a ativos de produção e trabalho.

### <a name="prerequisites"></a>Pré-requisitos

Para usar esse recurso, o sistema deve incluir o seguinte:

- Dynamics 365 Supply Chain Management versão 10.0.15 ou posterior
- [Gravação dupla](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) para aplicativos do Supply Chain Management.
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) versão 400.0.1.48 ou posterior

### <a name="turn-on-the-feature"></a>Ativar o recurso

Para disponibilizar o recurso no sistema, você deve habilitar suas chaves de configuração. Você precisa fazer isso apenas uma vez. Para isso, um administrador deve fazer o seguinte:

1. Coloque seu sistema em modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Vá para **Administração de sistema \> Configurar \> Configuração de licença**.
1. Expanda a seção **Realidade misturada** e marque a caixa de seleção **Guia de realidade misturada**.
1. Expanda a seção **Gerenciamento de produção** e marque a caixa de seleção **Instruções de produção**.
1. Desative o modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a>Configurar como os guias são exibidos no chão de fábrica

Para configurar como os guias são exibidos no chão de fábrica, acesse **Realidade misturada \> Dynamics 365 Guides \> Configurar a integração de guias**.

![Configurar a integração de guias para manufatura](media/instruction-guides-configure-integration.png "Configurar a integração de guias para manufatura")

Defina os seguintes campos:

- **URL do Microsoft Dataverse** - especifique a URL do ambiente do Microsoft Dataverse em que você cria o Guides. O formato é "contoso.crm4.dynamics.com", em que a primeira parte da URL normalmente é chamada de organização (como "contoso."), a segunda parte é específica da região de dados do ambiente (por exemplo, "crm4.") e a última parte é o domínio (como "dynamics.com"). Uma forma de encontrar a URL certa é acessar [home.dynamics.com](https://home.dynamics.com/) e abrir o aplicativo Guides. Quando o Guides for aberto, você verá a URL na barra de endereços do navegador (só considere a URL básica, que deve ser semelhante ao exemplo anterior). Esse valor é usado para compor os endereços das guias e será codificado nos códigos QR.
- **Código QR** - Defina o tamanho do código QR renderizado. É recomendável escolher um tamanho que ocupará a maior parte da tela de exibição, mas não mais. Normalmente, *15* é um bom valor.
- **Nível de correção de erro do código QR** - Defina a granularidade do código QR. A granularidade mais alta pode ajudar a aumentar a confiabilidade do código, mas o seu **tamanho de código QR** deve ser grande o suficiente para oferecer suporte ao nível de detalhes exigido pelo nível de correção selecionado.

> [!TIP]
> - Os tamanhos de código QR que são grandes demais para sua tela demorarão um pouco mais para serem processados e serão redimensionados para se ajustarem à tela. Eles não oferecem uma vantagem.
> - Os tamanhos de código QR que são muito pequenos podem diminuir a capacidade de o HoloLens ler o código adequadamente em alguns ambientes.
> - Recomendamos que você teste as configurações de cada dispositivo que exibirá os códigos QR para os usuários do HoloLens. Escolha as configurações que oferecem legibilidade suficiente no seu ambiente de chão de fábrica.  

## <a name="get-an-overview-of-all-guide-assignments"></a>Obter uma visão geral de todas as atribuições de guias

Use a página **Todos os guias** para ver a lista de todos os guias disponíveis na sua organização e todas as atribuições aos seus processos e recursos de produção. Para abri-la, acesse **Realidade misturada \> Guias \> Todos os guias**. A lista na parte superior mostra todos os guias disponíveis, e você pode usar o campo aqui para filtrar a lista. A lista na parte inferior mostra todas as atribuições de guias e fornece uma barra de ferramentas para gerenciá-las.

![Gerenciar guias](media/instruction-guides-allguides.png "Gerenciar guias")

As seções a seguir descrevem os tipos de objetos para os quais você pode atribuir guias. Cada guia atribuído fornece instruções anexadas automaticamente aos respectivos trabalhos de produção e estarão disponíveis no chão de fábrica.

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a>Associar um guia a um recurso

Adicione um guia a um [recurso](operations-resources.md) para oferecer o guia no contexto de trabalhos de produção relevantes.

### <a name="typical-scenario-using-resources"></a>Cenário típico usando recursos

Por exemplo, você pode anexar um guia com instruções gerais de segurança ou manipulação de máquinas a um recurso do tipo de máquina. Em seguida, o guia estará disponível em cada trabalho que for executado no computador.

### <a name="add-a-guide-to-a-resource"></a>Adicionar um guia a um recurso

Para adicionar um guia a um recurso:

1. Acesse **Controle de produção \> Configuração \> Recursos \> Recursos**.
1. No painel de lista, selecione o recurso para o qual deseja atribuir um guia.
1. Expanda a FastTab **Guias associados**.
1. Selecione **Adicionar** na barra de ferramentas **Guias associados**. Uma nova linha é adicionada à grade.
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir. Se você tiver muitos guias, poderá filtrar a lista para localizar o que está procurando.
    ![Gerenciar guias](media/instruction-guides-allguides.png "Gerenciar guias")

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a>Associar um guia a um grupo de recursos

Você pode adicionar um guia aos [grupos de recursos](tasks/define-discrete-manufacturing-resource-group.md), se usá-los para gerenciar grupos de máquinas, linhas de produção ou células de trabalho.

### <a name="typical-scenarios-using-resource-groups"></a>Cenários típicos usando grupos de recursos

**Exemplo 1:** você definiu um grupo de recursos para várias máquinas do mesmo modelo. Em vez de atribuir o guia relevante de instruções de manuseio para o modelo de máquina a cada recurso relevante, você pode atribuí-lo ao grupo de recursos que reflete esse modelo de máquina.

**Exemplo 2:** você definiu um grupo de recursos para uma célula de trabalho que contém máquinas diferentes e tem um guia que fornece instruções gerais sobre como manter a célula de trabalho. O guia se aplica a qualquer atividade de produção nesta célula de trabalho.

### <a name="add-a-guide-to-a-resource-group"></a>Adicionar um guia a um grupo de recursos

Para adicionar um guia a um grupo de recursos:

1. Acesse **Controle de produção \> Configuração \> Recursos \> Grupos de recursos**.
1. No painel de lista, selecione o grupo de recursos para o qual deseja atribuir um guia.
1. Expanda a FastTab **Guias associados**.
1. Selecione **Adicionar** na barra de ferramentas **Guias associados**. Uma nova linha é adicionada à grade.
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir. Se você tiver muitos guias, poderá filtrar a lista para localizar o que está procurando.
    ![Adicionar um guia a um grupo de recursos](media/instruction-guides-resourcegroup.png "Adicionar um guia a um grupo de recursos")

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a>Associar um guia a um produto liberado

Você pode adicionar um guia a qualquer [produto liberado](../pim/tasks/create-released-product-single-company.md).

### <a name="typical-scenario-using-released-products"></a>Cenário típico usando produtos liberados

Os guias de nível de produto ajudam os trabalhadores do chão de fábrica com instruções relevantes para operar ou manusear um produto ou item específico liberado.

### <a name="add-a-guide-to-a-released-product"></a>Adicionar um guia a um produto liberado

Para adicionar um guia a um produto liberado:

1. Vá para **Gerenciamento de informações de produção \> Produtos \> Produtos liberados**.
1. Abra o produto ao qual você deseja atribuir um guia.
1. No Painel de ações, abra a guia **Engenheiro** e, no grupo **Exibir**, selecione **Guias associados**.
1. A página **Guias associados** é aberta para o produto selecionado.
1. Selecione **Adicionar** no Painel de ações para adicionar uma nova linha à grade. 
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.
    ![Adicionar um guia a um produto liberado](media/instruction-guides-ReleasedProduct-AddGuides.png "Adicionar um guia a um produto liberado")

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a>Associar um guia a uma fórmula

Você pode adicionar um guia a qualquer [fórmula](bill-of-material-bom.md#formulas-co-products-and-by-products).

### <a name="typical-scenario-using-formulas"></a>Cenário típico usando fórmulas
  
Os guias de nível de fórmula oferecem aos funcionários de chão de fábrica as instruções orientadas sobre manuseio no contexto de uma fórmula ou receita. Os guias também podem ser atribuídos a versões de uma fórmula.

> [!NOTE]
> Você pode atribuir orientações relevantes para processos de produção com base em uma fórmula a um roteiro, uma versão de roteiro ou relações de operação de roteiro.  

> Não é possível anexar guias a linhas individuais de fórmulas no momento.

### <a name="add-a-guide-to-a-formula"></a>Adicionar um guia a uma fórmula

Para adicionar um guia a uma fórmula:

1. Acesse **Gerenciamento de informações de produção \> Listas de materiais e fórmulas \> Fórmulas**.
1. Abra a fórmula à qual você deseja atribuir um guia.
1. Abra a guia **Cabeçalho** acima da FastTab superior.
1. Expanda a FastTab **Guias associados**.
1. Selecione **Adicionar** na barra de ferramentas **Guias associados**. Uma nova linha é adicionada à grade.
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.
    ![Adicionar um guia a uma fórmula](media/instruction-guides-Formula.png "Adicionar um guia a uma fórmula")

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a>Associar um guia a uma versão de fórmula

Você pode adicionar um guia a qualquer [versão de fórmula](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-formula-versions"></a>Cenário típico usando versões de fórmula

Os guias anexados a uma versão individual de uma fórmula oferecem aos trabalhadores de chão de fábrica as instruções que orientam sobre a produção dessa versão da receita de fórmula.

> [!TIP]
> Você pode atribuir orientações relevantes para processos de produção com base nesta versão de fórmula a um roteiro, uma versão de roteiro ou relações de operação de roteiro.  

> [!NOTE]
> Não é possível anexar guias a linhas individuais de fórmulas no momento.

### <a name="add-a-guide-to-a-formula-version"></a>Adicionar um guia a uma versão de fórmula

Para adicionar um guia a uma versão de fórmula:

1. Acesse **Gerenciamento de informações de produção \> Listas de materiais e fórmulas \> Fórmulas**.
1. Abra a fórmula que inclui uma versão à qual você deseja atribuir um guia.
1. Abra a guia **Cabeçalho** acima da FastTab superior.
1. Na FastTab **Versões da fórmula**, selecione a versão à qual você deseja atribuir um guia.
1. Na barra de ferramentas **Versões de fórmula**, selecione **Guias associados**.
    ![Abrir os guias associados a uma versão de fórmula selecionada](media/instruction-guides-FormulaVersion.png "Abrir os guia associados a uma versão de fórmula selecionada")
1. A página **Guias associados** é aberta para a versão de fórmula.
1. Selecione **Adicionar** no Painel de ações para adicionar uma nova linha à grade. 
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.
    ![Adicionar um guia a uma versão de fórmula](media/instruction-guides-FormulaVersionAddGuide.png "Adicionar um guia a uma versão de fórmula")

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a>Associar um guia a uma lista de materiais

Você pode adicionar um guia a qualquer [lista de materiais](bill-of-material-bom.md) (BOM).

### <a name="typical-scenario-using-bills-of-materials"></a>Cenário típico usando listas de materiais

Os guias anexados a uma BOM oferecem aos trabalhadores de chão de fábrica as instruções que explicam como preparar e manusear o material de uma BOM. Os guias também podem ser atribuídos a versões de uma BOM.

> [!NOTE]
> Não é possível anexar guias a linhas individuais de BOM no momento.

### <a name="add-a-guide-to-a-bill-of-materials"></a>Adicionar um guia a uma lista de materiais

Para adicionar um guia a uma lista de materiais:

1. Acesse **Gerenciamento de informações de produção \> Listas de materiais e fórmulas \> Listas de materiais**.
1. Abra a lista de materiais à qual você deseja atribuir um guia.
1. Abra a guia **Cabeçalho** acima da FastTab superior.
1. Expanda a FastTab **Guias associados**.
1. Selecione **Adicionar** na barra de ferramentas **Guias associados**. Uma nova linha é adicionada à grade.
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.
    ![Adicionar um guia a uma BOM](media/instruction-guides-BOM.png "Adicionar um guia a uma BOM")

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a>Associar um guia a uma versão de lista de materiais

Você pode adicionar um guia a qualquer [versão de lista de materiais](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-bill-of-materials-versions"></a>Cenário típico usando versões de lista de materiais

Os guias anexados a uma versão individual de BOM oferecem aos trabalhadores de chão de fábrica as instruções que explicam como preparar e manipular o material para uma versão de uma BOM diferente da BOM genérica ou de outras versões dela.

> [!NOTE]
> Não é possível anexar guias a linhas individuais de BOM no momento.

### <a name="add-a-guide-to-a-bill-of-materials-version"></a>Adicionar um guia a uma versão de lista de materiais

Para adicionar um guia a uma versão de lista de materiais:

1. Acesse **Gerenciamento de informações de produção \> Listas de materiais e fórmulas \> Listas de materiais**.
1. Abra a BOM que inclui uma versão à qual você deseja atribuir um guia.
1. Abra a guia **Cabeçalho** acima da FastTab superior.
1. Na FastTab **Versões de BOM**, selecione a versão à qual você deseja atribuir um guia.
1. Na barra de ferramentas **Versões de BOM**, selecione **Guias associados**.
    ![Abrir os guias associados a uma versão de BOM selecionada](media/instruction-guides-BOMVersion.png "Abrir os guias associados a uma versão de BOM selecionada")
1. A página **Guias associados** é aberta para a versão de BOM.
1. Selecione **Adicionar** no Painel de ações para adicionar uma nova linha à grade.
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.
    ![Adicionar um guia a uma versão de BOM](media/instruction-guides-BOMVersionAddGuide.png "Adicionar um guia a uma versão de BOM")

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a>Associar um guia a um roteiro

Você pode adicionar um guia a qualquer [roteiro](routes-operations.md).

### <a name="typical-scenario-using-routes"></a>Cenário típico usando roteiros

Normalmente, os roteiros são usados para especificar como um determinado produto liberado deve ser produzido com base em uma BOM ou em uma versão de BOM e com um conjunto de recursos ou grupos de recursos.

Atribua um guia a um roteiro para oferecer instruções passo a passo para o respectivo processo de produção.

### <a name="add-a-guide-to-a-route"></a>Adicionar um guia a um roteiro

Para adicionar um guia a um roteiro:

1. Acesse **Controle de produção \> Todos os roteiros**.
1. Abra o roteiro ao qual você deseja atribuir um guia.
1. Expanda a FastTab **Guias associados**.
1. Selecione **Adicionar** na barra de ferramentas **Guias associados**. Uma nova linha é adicionada à grade.
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.
    ![Adicionar um guia a um roteiro](media/instruction-guides-Route.png "Adicionar um guia a um roteiro")

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a>Associar um guia a uma versão de roteiro

Você pode adicionar um guia a qualquer [versão de roteiro](routes-operations.md#route-versions).

### <a name="typical-scenario-using-route-versions"></a>Cenário típico usando versões de roteiro

Normalmente, as versões de roteiro são usadas para especificar grades de processos de produção com base em um roteiro existente. Você pode atribuir guias diferentes a cada versão de roteiro.

### <a name="add-a-guide-to-a-route-version"></a>Adicionar um guia a uma versão de roteiro

Para adicionar um guia a uma versão de roteiro:

1. Acesse **Controle de produção \> Todos os roteiros**.
1. Abra o roteiro ao qual você deseja atribuir um guia.
1. Na FastTab **Versões**, selecione a versão à qual você deseja atribuir um guia.
1. Na barra de ferramentas **Versões**, selecione **Guias associados**.
    ![Abrir os guias associados a uma versão de roteiro selecionada](media/instruction-guides-RouteVersion.png "Abrir os guias associados a uma versão de roteiro selecionada")
1. A página **Guias associados** é aberta para a versão de BOM.
1. Selecione **Adicionar** no Painel de ações para adicionar uma nova linha à grade.
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir.
    ![Adicionar um guia a uma versão de roteiro](media/instruction-guides-RouteVersionAddGuide.png "Adicionar um guia a uma versão de roteiro")

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a>Associar um guia a uma relação de operação de roteiro

Você pode adicionar um guia a qualquer [relação de operação de roteiro](routes-operations.md#operation-relations).

### <a name="typical-scenario-using-route-operation-relations"></a>Cenário típico usando relações de operação de roteiro

As relações de operação são a maneira mais específica de adicionar orientações a um processo de produto e suas operações relacionadas. Você pode especificar orientações para cada operação em um roteiro e especificar orientações diferentes para qualquer tipo de contexto de relação especificado para um roteiro, como para configurações, itens específicos e muito mais. Você também pode especificar a quais estágios da operação as orientações se aplicam (como configuração, enfileiramento, processo ou transporte).

> [!NOTE]
> Se você especificar guias para várias relações de operação de um roteiro, entre esses guias, somente o guia da relação mais específica será exibido no chão de fábrica para o trabalho gerado.

### <a name="add-a-guide-to-a-route-operation-relation"></a>Adicionar um guia a uma relação de operação de roteiro

Para adicionar um guia a uma relação de operação de roteiro:

1. Acesse **Controle de produção \> Todos os roteiros**.
1. Abra o roteiro ao qual você deseja atribuir um guia.
1. No Painel de ações, abra a guia **Roteiro** e, no grupo **Manter**, selecione **Detalhes do roteiro**.
1. A **Detalhes do roteiro** é aberta para o roteiro selecionado.
1. Na grade superior, selecione a operação para a qual você deseja oferecer orientações.
1. Na grade inferior, selecione uma relação específica (ou a relação genérica **Todos**).
    ![Selecionar uma operação e uma relação](media/instruction-guides-RouteOperationRelation.png "Selecionar uma operação e uma relação")
1. Acima da grade inferior, abra a guia **Guias associados**. ![A guia Guias associados](media/instruction-guides-RouteOperationRelation-AddGuide.png "A guia Guias associados")
1. Selecione **Adicionar** na barra de ferramentas na parte superior da grade inferior para adicionar uma nova linha à grade.
1. Para a nova linha, use a lista suspensa na coluna **Nome** para escolher o guia que você deseja atribuir. No restante da linha, marque a caixa de seleção para cada contexto em que o guia selecionado deve estar disponível.

> [!NOTE]
> Você pode adicionar um ou mais guias para cada estágio de cada operação.

## <a name="select-guides-from-the-shop-floor-execution-interface"></a>Selecionar guias na interface de execução do chão de fábrica

Quando um trabalhador abre uma lista de trabalhos na interface de execução do chão de fábrica, o Supply Chain Management localiza os guias relevantes para os trabalhos exibidos. Use o botão **Guias** para exibir os guias relevantes.

![O botão Guias na interface de execução do chão de fábrica](media/instruction-guides-Shopfloor1.png "O botão Guias na interface de execução do chão de fábrica")

Em seguida, coloque um HoloLens e acesse o respectivo guia ao olhar para o código QR e ative o respectivo guia.

![Código QR para acessar guias usando um HoloLens](media/instruction-guides-Shopfloor2.png "Código QR para acessar guias usando um HoloLens")

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a>Resolver a lógica para selecionar guias

Você pode adicionar guias aos seguintes dados de produção:

- [Recursos](#resources)
- [Grupos de recursos](#resource-groups)
- [Produtos liberados](#released-products)
- [Fórmulas](#formulas)
- [Versões da fórmula](#formula-versions)
- [Listas de materiais (BOMs)](#bom)
- [Versões da BOM](#bom-versions)
- [Roteiros](#routes)
- [Versões de roteiro](#route-versions)
- [Relações da operação de roteiro](#route-operation-relations)

Quando o Supply Chain Management gera os trabalhos para o chão de produção, ele coleta os guias relevantes dessas fontes. Anote as seguintes regras importantes:

- Se você anexar uma versão de BOM ou uma versão de fórmula a um roteiro ou a uma ordem de produção, qualquer guia associado a essa versão, e também os guias anexados à BOM ou fórmula pai dessa versão, será exibido no trabalho.
- Se você anexar uma versão de roteiro a uma ordem de produção, qualquer guia associado a essa versão, e também os guias anexados ao roteiro pai dessa versão, será exibido no trabalho.
- Se você definir várias relações de operação de roteiro que incluem a relação *Todos* e atribuir guias a elas, somente os guias da relação mais específica serão exibidos para o trabalho.  

![Diagrama para resolver os guias relevantes](media/instruction-guides-Resolve.png "Diagrama para resolver os guias relevantes")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]