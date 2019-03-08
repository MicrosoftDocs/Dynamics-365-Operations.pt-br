---
title: Layouts de tela para o ponto de venda (PDV)
description: Este tópico fornece informações sobre layouts de tela para experiências com o PDV (ponto de venda) do Microsoft Dynamics 365 for Retail.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 91d6e34c25710716788542dabb3bd7d935b2d4ab
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "321883"
---
# <a name="screen-layouts-for-the-point-of-sale-pos"></a>Layouts de tela para o ponto de venda (PDV)

[!include [banner](includes/banner.md)]

Este tópico fornece informações sobre layouts de tela para experiências com o PDV (ponto de venda) do Microsoft Dynamics 365 for Retail.

A interface de usuário do Retail POS pode ser configurada usando uma combinação de perfis visuais e layouts de tela que são atribuídos a lojas, caixas registradoras e/ou usuários.

A ilustração a seguir mostra as relações entre as várias entidades que compõem os aspectos configuráveis da interface do usuário do PDV.

![Entidades do layout da tela do PDV](../retail/media/POS-layout-configuration-entities-diagram.png)

## <a name="visual-profile"></a>Perfil visual

Os perfis visuais são atribuídos às caixas registradoras e usados para especificar os elementos visuais que são específicos da caixa registradora e compartilhados entre os usuários. Todo usuário que entrar na caixa registradora terá o mesmo tema, cores e imagens.

![Tela de boas-vindas do PDV com tema Claro](../retail/media/POS-Welcome-Screen-with-Light-theme.png)

![Tela de transação do PDV com tema Escuro](../retail/media/POS-Transaction-Screen-with-Dark-theme.png)

- **Número do perfil** – o número do perfil é o identificador exclusivo do perfil visual.
- **Descrição** – você pode especificar um nome significativo que ajudará a identificar o perfil correto de sua situação.
- **Tema** – os usuários podem selecionar entre os temas de aplicativo Claro ou Escuro. O tema afetará as cores da fonte e o plano de fundo em todo o aplicativo.
- **Cor de destaque** – a cor de destaque é usada em todo o PDV para diferenciar ou destacar elementos visuais específicos, como blocos, botões de comando e hyperlinks. Normalmente, esses elementos são acionáveis.
- **Cor do cabeçalho** – você pode configurar a cor do cabeçalho da página para atender aos requisitos de identidade visual do varejista. Este recurso está disponível somente na versão 1611 do Microsoft Dynamics 365 for Retail.
- **Segundo plano de logon** – você pode especificar uma imagem de plano de fundo para a tela de entrada. O tamanho do arquivo de imagens de plano de fundo deve ser o menor possível, pois armazenar e carregar arquivos grandes pode afetar o comportamento e o desempenho do aplicativo.
- **Plano de fundo do aplicativo** – você pode especificar uma imagem de plano de fundo para ser usada no lugar da cor sólida do tema no aplicativo. Quanto ao segundo plano de logon, o tamanho do arquivo deve ser o menor possível.

## <a name="screen-layouts"></a>Layouts da tela

As configurações do layout de tela determinam as ações, conteúdo e posicionamento dos controles de IU na tela de boas-vindas do PDV e na tela de **transação**.

![Exibição do layout da tela do PDV](../retail/media/POS-Screen-Layout-View.png)

- **Tela de boas-vindas** – na maioria dos casos, a tela de boas-vindas é a página que os usuários verão ao entrar pela primeira vez no PDV. A tela de boas-vindas pode ter uma imagem da marca e grades de botões que fornecem acesso às operações do PDV. Normalmente, operações que não são específicas à transação atual são colocadas nessa tela.

    ![Tela de boas-vindas do PDV](../retail/media/POS-Welcome-Screen.png)

- **Tela de transação** – a tela de **transação** é a tela principal no PDV para processar transações de vendas e ordens. O conteúdo e o layout são configurados usando-se o designer de layout de tela.

    ![Tela de transação de PDV](../retail/media/POS-Transaction-Screen.png)

- **Tela inicial padrão** – alguns varejistas preferem que os caixas acessem diretamente a tela de **transação** depois que fizerem logon. A configuração da **Tela inicial padrão** permite especificar a tela padrão que será exibida após o logon para cada layout da tela.

### <a name="assignment"></a>Atribuição

Os layouts de tela podem ser atribuídos à loja, registro ou nível de usuário. A atribuição de usuário substitui as atribuições de caixa registradora e de loja, e a atribuição de caixa registradora substitui a atribuição de loja. Em um cenário simples, em que todos os usuários usam o mesmo layout independentemente da caixa registradora ou da função, o layout da tela pode ser definido apenas no nível da loja. Em cenários em que as caixas registradoras ou usuários específicos precisam de layouts especializados, é possível atribuí-los.

### <a name="layout-sizes"></a>Tamanhos de layout

A maioria dos aspectos da interface do usuário do PDV são responsivos, e o layout é automaticamente redimensionado e ajustado com base no tamanho e orientação da tela. No entanto, a tela de **transação** do PDV deve ser configurada para cada resolução de tela esperada.

Durante a inicialização, o aplicativo de PDV selecionará automaticamente o tamanho de layout mais próximo que estiver configurado para o dispositivo. Um layout de tela também pode conter configurações para os modos paisagem e retrato, e para dispositivos com tamanho de tela normal e compacta. Portanto, é possível atribuir aos usuários um único layout de tela que funciona em vários tamanhos e fatores forma que são usados na loja.

![Tamanhos de layout do PDV](../retail/media/POS-Screen-Layout-Sizes.png)

- **Nome** – você pode inserir um nome significativo para identificar o tamanho da tela.
- **Tipo de layout** – o aplicativo de PDV pode exibir a interface do usuário em vários modos para fornecer a melhor experiência de usuário em um determinado dispositivo.

    - **Modern POS – Completo** – layouts completos geralmente são melhores para telas maiores, como monitores de desktop e tablets. Você pode selecionar elementos de interface de usuário a serem incluídos, especificar o tamanho e o posicionamento desses elementos e configurar as propriedades detalhadas. Os layouts completos suportam configurações de retrato e de paisagem.
    - **Modern POS – Compacto** – layouts compactos geralmente são melhores para telefones e tablets pequenos. As possibilidades de design para dispositivos compactos são limitadas. Você pode configurar as colunas e campos para os painéis de recebimento e de totais.

- **Largura/altura** – esses valores representam o tamanho efetivo da tela, em pixels, que é esperado para o layout. Lembre-se de que alguns sistemas operacionais usam a escala para telas de alta resolução.

> [!TIP]
> Você pode saber o tamanho de layout necessário para uma tela de PDV vendo a resolução no aplicativo. Inicie o PDV e acesse **Configurações \> Informações da sessão**. O PDV exibirá o layout de tela que está carregado no momento, o tamanho do layout, e a resolução da janela do aplicativo.

![Tamanhos de layout do PDV](../retail/media/POS-Session-Information.png)

### <a name="button-grids"></a>Grades de botões

Para cada tamanho de layout em um layout de tela, é possível configurar e atribuir grades de botões para a tela de boas-vindas do PDV e para a tela de **transação**. As grades de botões da tela de boas-vindas são apresentadas automaticamente da esquerda para a direita, partindo do número mais baixo (Tela de boas-vindas 1) para o número mais alto.

Em layouts de PDV completos, o posicionamento das grades de botões é especificado no designer de layout de tela.

Em layouts de PDV compactos, as grades de botões são apresentadas automaticamente de cima para baixo, partindo do número mais baixo (Tela de transação 1) para o número mais alto. Elas podem ser acessadas no menu **Ações** .

![Grades de botões de layout compacto](../retail/media/Compact-View-Button-Grids.png)

### <a name="images"></a>Imagens

Para cada tamanho de layout em um layout de tela, é possível especificar imagens a serem incluídas na interface do usuário do PDV. Para layouts de PDV completos, uma única imagem pode ser especificada para a tela de boas-vindas. Essa imagem aparecerá como o primeiro elemento de interface do usuário à esquerda. Na tela de **transação**, as imagens podem ser usadas como imagens de guia ou como um logotipo. Os layouts de PDV compactos não usam essas imagens.

### <a name="screen-layout-designer"></a>Designer do layout da tela

O designer de layout de tela permite configurar vários aspectos da tela de **transação** do PDV para cada tamanho de layout, tanto nos modos retrato e paisagem quanto nos layouts completo e compacto. O designer de layout de tela usa a tecnologia de implantação ClickOnce para baixar, instalar e iniciar a versão mais recente do aplicativo toda vez que o usuário acessá-lo. Certifique-se de verificar os requisitos do navegador para ClickOnce. Alguns navegadores, como o Google Chrome, exigem extensões.

> [!IMPORTANT]
> Você deve configurar um layout de tela para todos os tamanhos de layout definidos e usados pelo PDV.

### <a name="full-layout-designer"></a>Designer de layout completo

O designer de layout completo permite que os usuários arrastem controles de interface do usuário para a tela de **transação** do PDV e definam as configurações desses controles.

![Designer de layout de PDV completo (modo paisagem)](../retail/media/POS-Full-Layout-Designer-Landscape.png)

- **Importação de layout/exportação de layout** – você pode importar e exportar designs de layout de tela do PDV como arquivos XML, para que possa reutilizá-los e compartilhá-los nos ambientes com facilidade. É importante importar designs de layout para os tamanhos corretos de layout. Caso contrário, os elementos da interface do usuário podem não se ajustar corretamente à tela.
- **Paisagem/retrato** – se o dispositivo de PDV permitir que os usuários alternem entre os modos paisagem e retrato, você deverá definir o layout da tela para cada modo. O PDV automaticamente detecta a rotação da tela e mostra o layout correto.
- **Grade do layout** – o designer de layout de PDV usa uma grade de 4 pixels. Os controles da interface do usuário "ajustam-se" à grade para ajudar você a alinhar o conteúdo corretamente.
- **Zoom do designer** – você pode ampliar ou reduzir o zoom da exibição do designer para melhorar a exibição do conteúdo na tela do PDV. Esse recurso é útil quando a resolução da tela no PDV é muito diferente da resolução da tela usada no designer.
- **Mostrar/ocultar a barra de navegação** – para layouts de PDV completos, é possível selecionar se a barra de navegação esquerda fica visível na tela de **transação** . Esse recurso é útil para telas que têm uma resolução mais baixa. Para definir a visibilidade, clique com o botão direito do mouse na barra de navegação no designer, e marque ou desmarque a caixa de seleção **Sempre visível**. Se a barra de navegação estiver oculta, os usuários do PDV ainda poderão acessá-la usando o menu na parte superior esquerda.

    ![Mostrar/ocultar a barra de navegação](../retail/media/Navigation-Bar.PNG)

- **Controles do PDV** – o designer de layout de PDV oferece suporte aos controles a seguir. Você pode configurar muitos controles clicando com o botão direito do mouse e usando o menu de atalho.

    ![Controles da interface do usuário do PDV](../retail/media/POS-UI-Controls.png)

    - **Teclado numérico** – o teclado numérico é o mecanismo principal para as entradas do usuário na tela de **transação** do PDV. Você pode configurar o controle para que o teclado numérico completo seja exibido. Essa opção é ideal para dispositivos com tela touch. Alternativamente, você pode configurá-lo de forma que somente o campo de entrada seja exibido. Nesse caso, um teclado físico é usado para as entradas. As configurações de teclado numérico estão disponíveis somente para layouts completos. Para layouts compactos, o teclado numérico completo é sempre exibido na tela de **transação**.
    - **Painel de totais** – você pode configurar o painel de totais em uma ou duas colunas para exibir valores como contagem de linhas, valor do desconto, encargos, subtotal e imposto. Os layouts compactos oferecem suporte somente a uma única coluna.
    - **Painel de recibo** – o painel de recibo contém as linhas de vendas, linhas de pagamento e informações de entrega dos produtos e serviços processados no PDV. Você pode especificar colunas, larguras e o posicionamento. Em layouts compactos, você também pode configurar informações adicionais que são exibidas na linha abaixo da linha principal.
    - **Cartão de cliente** – o cartão de cliente mostra informações sobre o cliente que está associado com a transação atual. Você pode configurar o cartão de cliente para ocultar ou exibir informações adicionais.
    - **Controle guia** – você pode adicionar o controle guia a um layout de tela, e depois colocar outros controles, como o teclado numérico, o cartão de cliente ou grades de botões nele. O controle guia é um contêiner que ajuda você a ajustar mais conteúdo à tela. O controle guia está disponível somente para layouts completos.
    - **Imagem** – você pode usar o controle de imagem para mostrar o logotipo da loja ou outra imagem da marca na tela de **transação**. O controle de imagem está disponível somente para layouts completos.
    - **Produtos recomendados** – se o controle de produtos recomendados estiver configurado para o ambiente, ele mostrará sugestões de produto com base em machine learning.
    - **Controle personalizado** – o controle personalizado age como um espaço reservado no layout de tela para permitir que você reserve espaço para conteúdo personalizado. O controle personalizado está disponível somente para layouts completos.

### <a name="compact-layout-designer"></a>Designer de layout compacto

Como o designer de layout, o designer de layout compacto permite que você configure o layout da tela do PDV para telefones e tablets pequenos. No entanto, nesse caso, o layout em si é fixo. Você pode configurar os controles no layout clicando com o botão direito do mouse e usando o menu de atalho. No entanto, não é possível usar operações de arrastar e soltar para o conteúdo adicional.

![Designer de layout compacto](../retail/media/Compact-Layout-Designer.png)

### <a name="button-grid-designer"></a>Designer de grade de botões

O designer de grade de botões permite que você configure grades de botões que podem ser usadas na tela de boas-vindas do PDV e na tela de **transação** nos layouts completo compacto. A mesma grade de botões pode ser usada em vários layouts e tipos de layout. Como o designer de layout de tela, o designer de grade de botões usa a tecnologia de implantação ClickOnce para baixar, instalar e iniciar a versão mais recente do aplicativo toda vez que o usuário acessá-lo. Certifique-se de verificar os requisitos do navegador para ClickOnce. Alguns navegadores, como o Google Chrome, exigem extensões.

![Designer de grade de botões](../retail/media/Button-Grid-Designer.png)

- **Novo botão** – clique para adicionar um novo botão à grade de botões. Por padrão, os novos botões são exibidos no canto superior esquerdo de grade. No entanto, você pode organizar os botões arrastando-os no layout.

    > [!IMPORTANT]
    > Os conteúdos da grade de botões podem se sobrepor. Ao organizar os botões, verifique se eles não ocultam outros botões.

- **Novo design** – clique para configurar automaticamente um layout de grade de botões especificando o número de botões por linha e coluna.
- **Propriedades do botão** – você pode configurar as propriedades do botão clicando com o botão direito do mouse no botão e usando o menu de atalho.

    > [!IMPORTANT]
    > Algumas configurações da grade de botões aplicam-se somente ao PDV Empresarial, não ao Retail Modern POS ou PDV em Nuvem.

    ![Propriedades dos botões da grade de botões](../retail/media/Button-grid-button-properties.png)

    - **Ação** – na lista de operações de PDV aplicáveis, selecione a operação que é invocada quando o botão é clicado no PDV.

        Para obter a lista de operações de PDV com suporte, consulte [Operações de PDV, online e offline](pos-operations.md).

    - **Parâmetros de ação** – algumas operações de PDV usam parâmetros adicionais quando são invocadas. Por exemplo, para a operação Adicionar produto, os usuários podem especificar o produto a ser adicionado.
    - **Texto do botão** – especifique o texto que aparece no botão no PDV.
    - **Ocultar o texto do botão** – use esta caixa de seleção para ocultar ou mostrar o texto do botão. O texto do botão geralmente fica oculto em botões pequenos que exibem somente um ícone.
    - **Dica de ferramenta** – especifique o texto de ajuda adicional que aparece quando os usuários passam o mouse sobre o botão.
    - **Tamanho em colunas/tamanho em linhas** – você pode especificar a altura e a largura do botão.

        ![Tamanhos de botão do PDV em linhas e colunas](../retail/media/POS-Button-Sizes-In-Rows-And-Columns.png)

    - **Fonte personalizada** – ao marcar a caixa de seleção **Habilitar fonte personalizada para o PDV**, você poderá especificar uma fonte diferente da fonte padrão do sistema do PDV.
    - **Tema personalizado** – por padrão, os botões do PDV usam a cor de destaque do perfil visual. Ao marcar a caixa de seleção **Usar tema personalizado**, você poderá especificar cores adicionais.

        > [!NOTE]
        > O Retail Modern POS e o PDV em Nuvem usam somente os valores **Cor do plano de fundo** e **Cor da fonte**

    - **Imagem do botão** – os botões podem incluir imagens ou ícones. Selecione entre as imagens disponíveis especificadas em **Varejo \> Configuração de canal \> Configuração do PDV \> PDV \> Imagens**.

![Grade de botões de exemplo no PDV](../retail/media/Example-Button-Grid-In-POS.png)

## <a name="additional-resources"></a>Recursos adicionais

[Instalar o designer de Layout do Retail POS](install-pos-layout-designer.md)
