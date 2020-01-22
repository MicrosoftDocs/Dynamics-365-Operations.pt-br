---
title: Personalizar a experiência do usuário
description: Este tópico explica como você pode personalizar o aplicativo.
author: jasongre
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac8f154fdf892553f69d135727589bf13efd6076
ms.sourcegitcommit: 34395464ec80cea800b953eae49af579d436fc1b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935456"
---
# <a name="personalize-the-user-experience"></a>Personalizar a experiência do usuário

[!include [banner](../includes/banner.md)]

Este tópico explica como você pode personalizar o aplicativo.

Há três classes básicas de personalizações.

- Personalizações efetuadas em uma página de configuração. Os exemplos incluem um tema de cores e o fuso horário.
- Personalizações relacionadas ao uso da página. Essas personalizações são conhecidas por *implícitas*. Por exemplo, o sistema controlará a largura das colunas de grade, se você ajustá-las, e o estado expandido ou recolhido das Guias Rápidas.
- Personalizações feitas por um usuário para modificar a aparência de uma página, alterando a maneira como um elemento aparece ou age nessa página. Isso costuma ser feito por meio de um modo de personalização interativo. Essas personalizações são conhecidas por *explícitas*. Por exemplo, o usuário pode adicionar, ocultar ou reorganizar elementos na página.

Cada personalização feita por um usuário destina-se somente a esse usuário, independentemente do tipo de personalização ou da empresa com a qual o usuário interage no momento. As alterações que um usuário faz em uma página não afetam outros usuários no sistema.

## <a name="system-wide-options-for-the-current-user"></a>Opções no nível do sistema para o usuário atual

A página **Opções do usuário** contém várias configurações do sistema para o usuário atual. Para abrir a página **Opções do usuário**, selecione o botão **Configurações** (símbolo de engrenagem) na barra de navegação e, depois, **Opções do usuário**. A página **Opções do usuário** tem quatro guias que contêm várias configurações de usuário:

- **Visual** – selecione um tema de cores e o tamanho padrão de elementos nas páginas.
- **Preferências** – selecione os valores padrão que são usados sempre que você abre o sistema. Esses valores incluem a empresa, a página inicial e o modo de exibição/edição padrão. (O modo de exibição/edição determina se uma página está bloqueada para exibição ou aberta para edição sempre que ela é aberta.) Esta guia também inclui opções para o idioma, o fuso horário, além de data, hora e formatos numéricos. Finalmente, esta guia inclui diversas preferências que variam de acordo com a versão.
- **Conta** – ajuste o nome do usuário e outras opções relacionadas à conta.
- **Fluxo de trabalho** – selecione opções relacionadas ao fluxo de trabalho.

Além de modificar as configurações de usuário, você também pode usar a página **Opções do usuário** para exibir e excluir seus dados de uso e personalizações. Apenas selecione **Dados de utilização** no Painel de Ação.

Enquanto você usa o aplicativo, muitas de suas seleções são armazenadas para facilitar o uso do sistema no futuro. Na guia **Personalização**, você pode exibir e gerenciar as alterações pessoais que fez nas páginas no sistema. Nesta guia, também é possível redefinir o recurso de textos explicativos (ou seja, as janelas pop-up que introduzem novos recursos do sistema). Você será alertado novamente sobre recursos encontrados anteriormente.

> [!NOTE]
> Se o recurso [Exibições salvas](saved-views.md) estiver ativado, você poderá exibir e gerenciar suas personalizações selecionando **Personalização** no Painel de Ação da página **Opções do usuário**.

## <a name="implicit-personalizations"></a>Personalizações implícitas

As personalizações implícitas são aquelas que você efetua ao interagir com controles que armazenam seu estado de visibilidade atual.

- **Colunas de grade** – você pode ajustar a largura de uma coluna em uma grade ao selecionar a barra de dimensionamento à esquerda ou à direita do cabeçalho da coluna e deslizá-la para a esquerda ou a direita até a largura de coluna desejada. O aplicativo armazena a largura que você define para uma coluna. Na próxima vez que você abrir a página que inclui essa grade, a coluna será redimensionada para essa largura.
- **Guias Rápidas** – algumas páginas têm seções expansíveis conhecidas como *Guias Rápidas*. O aplicativo armazena informações sobre as Guias Rápidas que você expandiu e recolheu. Na próxima vez que você abrir a página, as mesmas Guias Rápidas serão expandidas ou recolhidas, com base em sua última interação na página. Em alguns casos, você pode ajudar a melhorar o desempenho do sistema recolhendo uma Guia Rápida, pois o aplicativo não precisa recuperar as informações das Guias Rápidas até que elas sejam expandidas. Conforme explicado mais adiante neste tópico, também é possível alterar a ordem das Guias Rápidas em uma página.
- **Quadros de Fatos** – Algumas páginas têm um painel **Informações relacionadas** que exibe informações somente leitura relacionadas ao assunto atual da página. Cada seção no painel **Informações relacionadas** é conhecida como um *Quadro de Fatos*. Você pode expandir ou recolher o painel **Informações relacionadas** e também pode expandir ou recolher Quadros de Fatos individuais. O aplicativo armazena essas preferências. Dessa maneira, na próxima vez que você abrir a página, o painel **Informações relacionadas** e o Quadro de Fatos individual estarão expandidos ou recolhidos, de acordo com sua última interação na página. Em alguns casos, você pode ajudar a melhorar o desempenho do sistema recolhendo um Quadro de Fatos, pois o aplicativo não precisa recuperar as informações de Quadros de Fatos até que eles sejam expandidos.
- **Painéis de ações** – um *Painel de ações* aparece na parte superior da maioria das páginas. O Painel de ações contém botões para muitas das ações que você pode executar na página atual. Esses botões costumam ser organizados em guias. É possível "fixar" todo o Painel de Ação aberto ou deixá-lo recolhido por padrão. Na próxima vez que você abrir a página, o Painel de Ação estará aberto ou recolhido, de acordo com sua última interação na página. Se você fixou o Painel de Ação aberto, a última guia usada por você será exibida.
- **Filtros Rápidos** – um *Filtro Rápido* aparecerá acima de muitas grades. O Filtro Rápido permite filtrar a grade, com base em uma coluna selecionada. O aplicativo armazena a coluna em que você filtrou. Da próxima vez que você abrir a página que inclui essa grade, a grade será filtrada na mesma coluna. Entretanto, você pode selecionar uma coluna diferente com a qual filtrar a grade.
- **Filtros do cabeçalho de coluna** – Quando você filtra uma grade usando *filtros de cabeçalho de coluna*, é possível modificar o operador do filtro, conforme necessário, para localizar os dados desejados. Por exemplo, você pode alterar o operador de **inicia com** para **é exatamente**. Sempre que você usar um filtro de cabeçalho de coluna e alterar o operador de filtro, o aplicativo armazenará a alteração. Dessa maneira, da próxima vez que você filtrar essa coluna, o operador de filtro será restaurado.
- **Painel de navegação** – É possível abrir o *painel de navegação* selecionando o botão **Expandir o painel de navegação** na parte superior esquerda de qualquer página. (Esse botão às vezes é conhecido como _botão de **Menu**_, *hamburger*, *menu de hamburger* ou *botão de hamburger*.) Você pode fixar o painel de navegação aberto ou ele pode ficar recolhido por padrão. Depois de fixar o painel de navegação aberto, o aplicativo o manterá aberto até que você o recolha.

## <a name="explicit-personalizations"></a>Personalizações explícitas

Diferentes pessoas e empresas têm diferentes perspectivas em relação aos dados que são mais importantes para elas e aos dados que não são necessários para a maneira como realizam seus negócios. Você pode personalizar o modo como as informações são encomendadas e como você interage com elas. Você também pode especificar que algumas informações devam ser ocultas. Esses recursos são importantes para uma experiência pessoal e produtiva e são exemplos de personalizações explícitas. As personalizações explícitas são aquelas que você executa explicitamente, pois deseja alterar a aparência ou o comportamento de um elemento ou uma página.

### <a name="shortcut-menu-options"></a>Opções do menu de atalho

Os menus de atalho fornecem algumas maneiras de alterar explicitamente uma página, de modo que ela atenda melhor aos seus requisitos ou às necessidades de sua empresa. (Um menu de atalho também é conhecido como *menu do botão direito do mouse* ou *menu de contexto*.)

Algumas das alterações mais comuns e importantes a serem feitas em uma pagina estão disponíveis diretamente como opções em um menu de atalho. Por exemplo, a partir da atualização de plataforma 17, para adicionar ou ocultar colunas em uma grade, basta clicar com o botão direito do mouse no cabeçalho de uma coluna e selecionar **Adicionar colunas** ou **Ocultar esta coluna**.

Além disso, para disponibilizar os tipos mais básicos de personalização explícita, clique com o botão direito em um elemento e selecione **Personalizar**. (Observe que nem todos os elementos na página podem ser personalizados.) Quando você usar esse método de personalização, a janela de propriedades do elemento será exibida.

![Personalização de propriedades de um elemento](./media/personalization-element-properties.png)

Você pode usar a janela de propriedades para personalizar um elemento das seguintes maneiras:

- Alterar o rótulo do elemento.
- Ocultar o elemento para que ele não seja exibido na página. Os dados no campo não serão excluídos nem alterados. Apenas as informações não aparecerão mais na página.
- Incluir as informações na seção de resumo da Guia Rápida (se o elemento estiver em uma Guia Rápida).
- Ignorar o campo, de forma que ele nunca receba o foco quando você percorrer a página usando a tecla Tab.
- Evitar que os dados no campo sejam editados (para qualquer registro).

A janela de propriedades pode incluir outros recursos de personalização, dependendo do elemento. Por exemplo, a janela de propriedades para um bloco permitirá que você promova esse bloco para um painel. E a janela de propriedades para um painel permitirá que você crie um novo espaço de trabalho nesse painel.

### <a name="the-personalization-toolbar"></a>A barra de ferramentas de personalização

Se deseja fazer várias alterações em uma página ou fazer alterações que não estejam disponíveis por meio de outros mecanismos (por exemplo, se você deseja reordenar elementos), use a barra de ferramentas **Personalização**. Para abrir a barra de ferramentas **Personalização**, siga uma dessas etapas:

- Selecione **Personalizar este formulário** na janela de propriedades de um elemento.
- Selecione **Personalizar esta página** no grupo **Personalizar** da guia **Opções** no Painel de Ação de qualquer página.
- Selecione o botão **Configurações** (símbolo de engrenagem) na barra de navegação e selecione **Personalizar**.

[![Barra de ferramentas de personalização](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navegação na página

Quando a barra de ferramentas **Personalização** é aberta, a página subjacente é somente leitura (ou seja, você não pode editar os dados), mas ainda é interativa. Especificamente, é possível expandir ou recolher o painel **Informações relacionadas**, alternar guias e expandir ou recolher seções, da mesma maneira como executa normalmente essas ações na página. Para aplicar uma personalização a uma seção recolhível ou a uma guia (por exemplo, ocultar uma Guia Rápida), basta selecionar o botão exibido ao lado da seção ou da guia quando ela ganhar o foco do teclado ou quando você passar o mouse sobre ela.

#### <a name="personalization-tools"></a>Ferramentas de personalização

Estas ferramentas estão disponíveis na barra de ferramentas **Personalização**:

- Use a ferramenta **Selecionar** para selecionar e alterar as propriedades de um elemento. Para usar essa ferramenta, clique no botão **Selecionar** na barra de ferramentas e selecione o elemento desejado. A janela de propriedades do elemento será exibida e você poderá modificar qualquer uma das propriedades desse elemento. Você pode repetir o processo para outros elementos que possam ser personalizados nessa página. Observe que algumas propriedades de personalização podem não estar disponíveis em alguns cenários. Por exemplo, não é possível bloquear um campo obrigatório.
- Use a ferramenta **Ocultar** para ocultar um elemento na página. Para usar essa ferramenta, selecione o botão **Ocultar** na barra de ferramentas e selecione o elemento a ser ocultado. Quando você usa a ferramenta **Ocultar**, todos os elementos ocultos no momento ficam visíveis, mas são exibidos em um contêiner sombreado. Assim, você pode tornar um elemento visível selecionando-o. Para ver como a página ficará quando os elementos estiverem ocultos, alterne para outra ferramenta de personalização.
- Use a ferramenta **Adicionar um campo** para adicionar um campo à página. Ao usar esta ferramenta, você pode adicionar somente os campos que fazem parte da definição da página. Para obter informações sobre como criar novos campos que não fazem parte da definição de página atual, consulte [Criar e trabalhar com campos personalizados](user-defined-fields.md). Após selecionar o botão **Adicionar um campo** na barra de ferramentas, você deve primeiro selecionar o grupo ou a área em que deseja adicionar um campo. Uma caixa de diálogo mostrará a lista de campos relacionados ao grupo ou à área selecionada. Na caixa de diálogo, escolha um ou mais campos a serem adicionados e selecione **Inserir**. Para remover um campo adicionado anteriormente, repita o processo, mas desmarque a seleção do campo na caixa de diálogo.
- Use a ferramenta **Mover** para mover um elemento para um local diferente no grupo atual de elementos. Observe que não é possível mover um elemento para fora de seu grupo pai. Para usar essa ferramenta, selecione o botão **Mover** na barra de ferramentas e selecione o elemento a ser movido. Quando você seleciona um elemento, o aplicativo determina os locais para os quais o elemento pode ser movido. Esses locais são conhecidos como *zonas para soltar*. Quando você arrasta o elemento pelo grupo atual, cada zona para soltar é mostrada como uma linha colorida em negrito ao lado da área em que o elemento pode ser solto.
- Use a ferramenta **Ignorar** para remover um elemento da sequência de guias de teclado da página. Quando você seleciona o botão **Ignorar** na barra de ferramentas, todos os elementos ignorados no momento são exibidos em um contêiner sombreado. Você pode interativamente remover ou adicionar campos à sequência de guias.
- Use a ferramenta **Mostrar no cabeçalho** quando desejar que um campo seja exibido na seção de resumo da Guia Rápida. Quando você seleciona o botão **Mostrar no cabeçalho** na barra de ferramentas, todos os campos selecionados como campos de resumo são mostrados em um contêiner sombreado. Você pode interativamente adicionar e remover campos do resumo da Guia Rápida selecionando-os.
- Use a ferramenta **Bloquear** para marcar um elemento como editável ou não editável. Quando você seleciona o botão **Bloquear** na barra de ferramentas, todos os elementos não editáveis no momento são exibidos em um contêiner sombreado. Você poderá torná-los editáveis novamente. Observe que alguns campos são obrigatórios e não podem ser alterados para não editáveis. Um símbolo de cadeado aparece ao lado desses campos.
- Use o botão **Adicionar um PowerApp** para inserir na página um aplicativo criado usando o Microsoft PowerApps. Para obter informações detalhadas sobre como inserir um aplicativo do PowerApps em uma página, consulte [Inserir aplicativos do PowerApps](embed-power-apps.md).
- Use a ferramenta **Limpar** para redefinir a página para o estado padrão instalado. Todas as personalizações na página atual serão limpas. Não é possível desfaz a ação. Portanto, use essa ferramenta somente se tiver certeza de que deseja redefinir a página.
- Use a ferramenta **Importar** para carregar uma personalização de um arquivo que você ou outra pessoa criou anteriormente. Ao importar personalizações para uma página, é possível escolher se elas devem ser adicionadas ou se devem substituir todas as personalizações existentes na página. Não é possível desfaz a ação. Portanto, depois de importar as personalizações, você deve limpar ou desfazer manualmente todas as alterações que não desejar.
- Use a ferramenta **Exportar** para salvar as personalizações da página em um arquivo. Em seguida, você poderá compartilhar as personalizações com outros usuários. Esses usuários só precisam importar o arquivo que contém as personalizações da página.
- Selecione o botão **Fechar** para fechar a barra de ferramentas **Personalização** e retornar a página ao estado interativo anterior.

Tradicionalmente, quando a barra de ferramentas **Personalização** é usada, as personalizações entram em vigor assim que você as faz. Entretanto, se o recurso [Exibições salvas](saved-views.md) estiver ativado, você deverá salvar as personalizações explicitamente em uma exibição de sua preferência.

Em alguns casos, quando você seleciona uma ferramenta, aparece um símbolo de cadeado ao lado de um elemento. Esse símbolo indica que você não pode modificar as propriedades do elemento que estão relacionadas à ferramenta selecionada, pois as modificações nessas propriedades impedirão que a página funcione corretamente.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Como adicionar um bloco, uma lista ou um link a um espaço de trabalho

Para algumas páginas que incluem listas, o recurso de personalização **Adicionar ao espaço de trabalho** está disponível no grupo **Personalizar** da guia **Opções** no Painel de Ação. Esse recurso permite enviar por push as informações relevantes da lista atual para um espaço de trabalho específico. As informações exibidas no espaço de trabalho podem ser baseadas na lista inteira ou em uma versão classificada e filtrada da lista. Você também pode especificar se as informações aparecerão no espaço de trabalho como uma lista, um bloco resumido que pode mostrar o número de itens na lista ou um link.

> [!NOTE]
> Se o recurso [Exibições salvas](saved-views.md) estiver ativado, o conteúdo que você enviar por push para um espaço de trabalho será diretamente vinculado a uma exibição. A consulta da exibição é usada para buscar dados no espaço de trabalho e o bloco ou link correspondente no espaço de trabalho abre a página nessa exibição, de modo que a consulta e as personalizações da exibição sejam aplicadas a ela.

[![Adicionar ao espaço de trabalho](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Para adicionar uma lista a um espaço de trabalho, primeiro classifique ou filtre a lista na página de forma que ela mostre as informações como você deseja que apareçam no espaço de trabalho. (Se o recurso Exibições salvas estiver ativado, você não poderá prosseguir até salvar uma exibição com essas condições.) Em seguida, selecione **Adicionar ao espaço de trabalho**. Selecione um espaço de trabalho. No campo **Apresentação**, selecione **Lista**. Após você selecionar **Configurar**, aparecerá uma caixa de diálogo onde você poderá selecionar as colunas que devem aparecer na lista no espaço de trabalho. Você também pode especificar o rótulo usado para a lista no espaço de trabalho.
- Para adicionar um bloco a um espaço de trabalho, primeiro filtre a lista na página para que ela mostre os dados a serem resumidos ou que você deseja acessar rapidamente. (Se o recurso Exibições salvas estiver ativado, você não poderá prosseguir até salvar uma exibição com essas condições.) Em seguida, selecione **Adicionar ao espaço de trabalho**. Selecione um espaço de trabalho. No campo **Apresentação**, selecione **Bloco**. Após selecionar **Configurar**,uma caixa de diálogo será exibida onde você poderá especificar o rótulo a ser usado para o bloco no espaço de trabalho. Você também pode especificar se o bloco deve mostrar uma contagem. Depois de ser adicionado ao espaço de trabalho, o bloco poderá ser selecionado para abrir a página atual no espaço de trabalho. Você pode, então, exibir a lista filtrada associada ao bloco.
- Para adicionar um link a um espaço de trabalho, primeiro filtre a lista na página para que ela mostre os dados do seu interesse. (Se o recurso Exibições salvas estiver ativado, você não poderá prosseguir até salvar uma exibição com essas condições.) Em seguida, selecione **Adicionar ao espaço de trabalho**. Selecione um espaço de trabalho. No campo **Apresentação**, selecione **Link**. Após selecionar **Configurar**, uma caixa de diálogo será exibida onde você poderá especificar o rótulo a ser usado para o link. Você também pode, opcionalmente, especificar um rótulo para uma nova seção que tenha esse link.

Após adicionar uma lista, um bloco ou um link a um espaço de trabalho, você pode abrir esse espaço de trabalho e reorganizar os elementos nele como desejar.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Como adicionar um resumo de um espaço de trabalho a um painel

Alguns espaços de trabalho contêm blocos de contagem (isto é, blocos com números). Talvez você deseje que esse blocos apareçam também no painel. Em um espaço de trabalho, clique com o botão direito do mouse em um bloco de contagem, selecione **Personalizar** e, em seguida, na janela de propriedades do bloco, selecione **Fixar no painel**. Dessa maneira, na próxima vez que você abrir e atualizar o painel selecionado, a contagem aparecerá abaixo do bloco de navegação desse espaço de trabalho. Você pode selecionar essa contagem para ir diretamente para os dados que ela representa.

### <a name="personalizing-your-dashboard"></a>Como personalizar seu painel

Geralmente, o painel é a primeira página que você vê ao abrir o aplicativo. É possível personalizar o painel de forma que ele mostre apenas os blocos do espaço de trabalho que você deseja ver. Você também pode reorganizar os blocos na ordem em que preferir, renomear os blocos de navegação do espaço de trabalho ou adicionar um novo bloco de espaço de trabalho.

Para personalizar o painel, clique com o botão direito no bloco e selecione **Personalizar** para abrir a janela de propriedades do bloco.

- Se desejar ocultar ou renomear o bloco selecionado, você poderá fazer essa alteração diretamente na janela de propriedades.
- Para reordenar os blocos do espaço de trabalho, na janela de propriedades, selecione **Personalizar este formulário** para abrir a barra de ferramentas **Personalização**. Você poderá usar a ferramenta **Mover** para reorganizar os blocos como desejar.
- Para adicionar um novo bloco de espaço de trabalho, na janela de propriedades, selecione **Adicionar um espaço de trabalho**. Um novo bloco do espaço de trabalho será criado na parte inferior do painel. Você poderá renomear esse novo bloco do espaço de trabalho como desejar. Você também pode adicionar listas, blocos e links ao espaço de trabalho, conforme descrito na seção [Como adicionar listas, blocos e links a espaços de trabalho](#adding-a-tile-list-or-link-to-a-workspace) deste tópico.

## <a name="administration-of-personalizations"></a>Administração de personalizações

Após personalizar uma página, você pode compartilhar as personalizações com outros usuários exportando a página personalizada. Você pode solicitar que outros usuários abram a página personalizada e importem o arquivo personalização que você criou. Outra opção é ceder suas personalizações a um usuário que possua privilégios de administrador. Esse usuário poderá aplicar seu arquivo de personalização a vários usuários ao mesmo tempo.

Os usuários com privilégios de administrador também podem gerenciar personalizações para outros usuários na página **Personalização**.

Para os clientes que não ativaram o recurso [Exibições salvas](saved-views.md), essa página possui quatro guias:

- **Aplicar** – Você pode importar ou selecionar uma personalização de um ou mais usuários. Para aplicar uma personalização a um ou mais usuários, primeiro selecione uma função e os usuários que tenham essa função. Em seguida, selecione uma personalização existente para aplicar aos usuários selecionados ou importe um arquivo de personalização. A personalização será validada e aplicada a todos os usuários selecionados na próxima vez que eles abrirem a página selecionada.
- **Limpar** – você pode limpar todas as personalizações de uma página ou espaço de trabalho para um ou mais usuários. Primeiro, selecione uma página ou espaço de trabalho para ver uma lista de usuários que personalizaram essa página ou espaço de trabalho. Em seguida, selecione os usuários que devem ter as personalizações dessa página ou espaço de trabalho desmarcadas e selecione **Limpar**. Todas as personalizações que os usuários selecionados aplicaram à página ou ao espaço de trabalho selecionado serão excluídas. Essa ação não pode ser desfeita. Entretanto, se uma personalização tiver sido salva para a página ou o espaço de trabalho, essa personalização poderá ser reimportada.
- **Usuários** – Selecione um usuário para ver a lista de páginas que ele personalizou. Você pode habilitar ou desabilitar a capacidade de o usuário selecionado utilizar personalizações para páginas específicas ou para todo o sistema. Também é possível importar, exportar ou limpar uma personalização para o usuário. Além disso, você pode redefinir o recurso de textos explicativos para o usuário. Nesse caso, se o usuário tiver ignorado anteriormente qualquer janela pop-up que apresentava novos recursos, ela será exibida novamente na próxima vez que ele encontrar esses recursos.
- **Sistema** – É possível desativar temporariamente as personalizações de todos os usuários no sistema. Nesse caso, todas as personalizações são excluídas para todos os usuários e todas as páginas são redefinidos para seu estado padrão. Se, mais tarde, você ativar novamente a personalização, todas as personalizações serão reaplicadas. Também é possível excluir permanentemente todas as personalizações de todos os usuários do sistema. Não é possível recuperar as personalizações que foram excluídas. Portanto, antes de executar essa tarefa, verifique se você exportou todas as personalizações de que talvez precise posteriormente.

Para os clientes que ativaram o recurso [Exibições salvas](saved-views.md), a página **Personalização** possui cinco guias:

- **Exibições publicadas** – Essas exibições foram publicadas para a sua organização. Para alterar os usuários para os quais são destinadas essas exibições, você pode modificar as funções de segurança ou as entidades legais associadas a cada exibição. Também pode exportar ou excluir uma ou mais exibições publicadas.
- **Exibições não publicadas** – Essas são exibições de modelo que foram importadas para o sistema, mas ainda não foram publicadas. Você pode publicar, exportar ou excluir essas exibições.
- **Exibições pessoais** – Essas exibições foram criadas por usuários no sistema. Você pode publicar uma exibição pessoal para a organização ou copiar uma ou mais dessas exibições para outros usuários. Você também pode exportar ou excluir essas exibições, conforme necessário.
- **Usuários** – Selecione um usuário para ver a lista de páginas que ele personalizou. Você pode habilitar ou desabilitar a capacidade de o usuário selecionado utilizar personalizações para páginas específicas ou para todo o sistema. Também é possível importar, exportar ou limpar uma personalização para o usuário. Além disso, você pode redefinir o recurso de textos explicativos para o usuário. Nesse caso, se o usuário tiver ignorado anteriormente qualquer janela pop-up que apresentava novos recursos, ela será exibida novamente na próxima vez que ele encontrar esses recursos.
- **Sistema** – É possível desativar temporariamente as personalizações de todos os usuários no sistema. Nesse caso, todas as personalizações são excluídas para todos os usuários e todas as páginas são redefinidos para seu estado padrão. Se, mais tarde, você ativar novamente a personalização, todas as personalizações serão reaplicadas. Também é possível excluir permanentemente todas as personalizações de todos os usuários do sistema. Não é possível recuperar as personalizações que foram excluídas. Portanto, antes de executar essa tarefa, verifique se você exportou todas as personalizações de que talvez precise posteriormente.

Os usuários com acesso à página **Personalização** também podem importar exibições pessoais ou de modelo usando o botão **Importar exibições** no Painel de Ação.

## <a name="personalizing-inventory-dimensions"></a>Personalizar dimensões de estoque

Quando você personalizar a configuração de dimensões de estoque em uma página, considere as configurações que foram criadas usando a opção **Dimensões de exibição**. Por exemplo, você usou a personalização para ocultar uma coluna para a dimensão de estoque do número de lote, mas a coluna aparecerá na próxima vez que a página for aberta. Esse comportamento ocorre porque as configurações **Exibição de dimensão** controlam as colunas de dimensão do estoque que são exibidas. As configurações de **Exibição de dimensão** se aplicam a todas as páginas e substituem qualquer configuração personalizada de campos de dimensão de estoque em páginas individuais.

Portanto, no exemplo anterior, se você não deseja que a coluna da dimensão de estoque do número de lote apareça na página, limpe essa dimensão como parte da opção **Exibir dimensões** dessa página.
