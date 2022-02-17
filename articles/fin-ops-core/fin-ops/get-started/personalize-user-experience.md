---
title: Personalizar a experiência do usuário
description: Este tópico explica como você pode personalizar o aplicativo.
author: jasongre
ms.date: 01/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 840a68d506664043c9affb67e801429e0594f0bd
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075413"
---
# <a name="personalize-the-user-experience"></a>Personalizar a experiência do usuário

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Este tópico explica como você pode personalizar o aplicativo e aborda os seguintes assuntos: 

- **Opções de todo o sistema** — essas opções de personalização são feitas em uma página de configuração e estão disponíveis para todos os usuários. Os exemplos incluem um tema de cores e o fuso horário. 
- **Acesso restrito à personalização** — nesse nível de acesso, as ações do usuário associadas ao uso comum da página são salvas automaticamente pelo aplicativo e restauradas na próxima vez que você acessar a página. Por exemplo, o aplicativo armazenará a largura das colunas de grade, se você ajustá-las, e o estado expandido ou recolhido das Guias Rápidas. 
- **Acesso total à personalização** — nesse nível de acesso, os usuários têm acesso a todos os recursos de personalização no aplicativo. Particularmente, eles têm acesso à barra de ferramentas **Personalização**. 
- **Compartilhamento de personalizações** — os usuários com acesso total à personalização podem exportar suas personalizações de página e compartilhá-las com outros usuários.
- **Administração de personalizações** — os usuários privilegiados podem acessar a página de administração de **Personalização** para gerenciar todas as personalizações em um nível organizacional. 

## <a name="system-wide-options-for-the-current-user"></a>Opções no nível do sistema para o usuário atual

A página **Opções do usuário** contém várias configurações do sistema para o usuário atual. Essas opções estão disponíveis para todos os usuários, mesmo aqueles que não receberam nenhum acesso à personalização. Para abrir a página **Opções do usuário**, selecione o botão **Configurações** na barra de navegação e, depois, **Opções do usuário**. A página **Opções do usuário** tem quatro guias que contêm várias configurações de usuário:

- **Visual** – selecione um tema de cores e o tamanho padrão de elementos nas páginas.
- **Preferências** – selecione os valores padrão que são usados sempre que você abre o sistema. Esses valores incluem a empresa padrão, a página inicial e o modo de exibição/edição padrão. (O modo de exibição/edição determina se uma página está bloqueada para exibição ou aberta para edição sempre que ela é aberta.) Esta guia também inclui opções para o idioma, o fuso horário, além de data, hora e formatos numéricos. Finalmente, esta guia inclui diversas preferências que variam de acordo com a versão.
- **Conta** — exiba ou ajuste seu nome de usuário e outras opções relacionadas à conta.
- **Fluxo de trabalho** – selecione opções relacionadas ao fluxo de trabalho.

Além de alterar as configurações de usuário, você também pode exibir e excluir seus dados de uso e personalizações da página **Opções do usuário**. Para ver seus dados de uso, selecione **Dados de uso** no Painel de Ações. Na guia **Personalização**, você pode exibir e gerenciar as alterações pessoais que fez nas páginas no sistema. Nesta guia, também é possível redefinir o recurso de textos explicativos (ou seja, as janelas pop-up que introduzem novos recursos do sistema). Você será alertado novamente sobre recursos encontrados anteriormente.

> [!NOTE]
> Se o recurso [Exibições salvas](saved-views.md) estiver ativado, você poderá exibir e gerenciar suas personalizações selecionando **Personalização** no Painel de Ação da página **Opções do usuário**.

## <a name="restricted-personalization-access-formerly-implicit-personalizations"></a>Acesso restrito à personalização (conhecido anteriormente como personalizações implícitas)

No nível de **acesso restrito à personalização**, as ações do usuário associadas ao uso comum da página são salvas automaticamente pelo aplicativo e restauradas na próxima vez que você acessar a página. Nenhuma ação de salvamento explícita é necessária. 

Veja uma lista das ações que são consideradas uso comum de página e estão cobertas pelo acesso restrito à personalização: 

- **Larguras de colunas de grade** – você pode ajustar a largura de uma coluna em uma grade ao selecionar a barra de dimensionamento à esquerda ou à direita do cabeçalho da coluna e deslizá-la para a esquerda ou a direita até a largura de coluna desejada. O aplicativo armazena a largura que você define para uma coluna. Na próxima vez que você abrir a página, a coluna será redimensionada para essa largura.
- **Totais rodapé e da coluna de grade** — *(disponível somente quando o novo controle de grade estiver habilitado)* você pode decidir se um total deve ou não ser mostrado na parte inferior de qualquer coluna numérica em uma grade, bem como se o rodapé da grade deve ficar visível. O aplicativo armazena essas preferências e as aplica na próxima vez que você abrir a página. Para obter mais informações, consulte [Recursos de grade](grid-capabilities.md). 
- **Guias Rápidas** – algumas páginas têm seções expansíveis conhecidas como *Guias Rápidas*. O aplicativo armazena informações sobre as Guias Rápidas que você expandiu ou recolheu. Na próxima vez que você abrir a página, as mesmas Guias Rápidas serão expandidas ou recolhidas, com base em sua última interação na página. Em alguns casos, você pode ajudar a melhorar o desempenho do sistema recolhendo uma Guia Rápida, pois o aplicativo não precisa recuperar as informações das Guias Rápidas até que elas sejam expandidas. Conforme explicado mais adiante neste tópico, também é possível alterar a ordem das Guias Rápidas em uma página.
- **Quadros de Fatos** — algumas páginas têm um painel **Informações relacionadas** que exibe informações somente leitura relacionadas ao assunto atual da página. Cada seção no painel **Informações relacionadas** é conhecida como um *Quadro de Fatos*. Você pode expandir ou recolher o painel **Informações relacionadas** e também pode expandir ou recolher Quadros de Fatos individuais. O aplicativo armazena essas preferências. Na próxima vez que você abrir a página, o painel **Informações relacionadas** e o Quadro de Fatos individual estarão expandidos ou recolhidos, de acordo com sua última interação na página. Em alguns casos, você pode ajudar a melhorar o desempenho do sistema recolhendo o painel **Informações relacionadas** ou um Quadro de Fatos, pois o aplicativo não precisa recuperar as informações de Quadros de Fatos até que eles sejam expandidos.
- **Painéis de ações** – um *Painel de ações* aparece na parte superior da maioria das páginas. O Painel de ações contém botões para muitas das ações que você pode executar na página atual. Esses botões costumam ser organizados em guias. É possível *fixar* todo o Painel de Ações aberto ou deixá-lo recolhido por padrão. Na próxima vez que abrir a página, o Painel de Ações estará aberto ou recolhido, de acordo com sua última interação na página. Se você fixou o Painel de Ações aberto, a última guia que você estava usando será exibida.
- **Filtros Rápidos** – um *Filtro Rápido* aparecerá acima de muitas grades. O Filtro Rápido permite filtrar a grade, com base em uma única coluna selecionada. O aplicativo armazena a coluna em que você filtrou. Na próxima vez que você abrir a página, a grade usará a mesma coluna para a filtragem por padrão. No entanto, você ainda poderá selecionar uma coluna diferente com a qual filtrar a grade.
- **Filtros do cabeçalho de coluna** — quando você filtra uma grade usando *filtros de cabeçalho de coluna*, é possível alterar o operador do filtro, conforme necessário, para encontrar os dados desejados. Por exemplo, você pode alterar o operador de **inicia com** para **é exatamente**. Sempre que você usar um filtro de cabeçalho de coluna e alterar o operador de filtro, o aplicativo armazenará a alteração. Dessa maneira, da próxima vez que você filtrar essa coluna, o operador de filtro será restaurado.
- **Painel de navegação** – É possível abrir o *painel de navegação* selecionando o botão **Expandir o painel de navegação** na parte superior esquerda de qualquer página. (Esse botão às vezes é conhecido como _botão de **Menu**_, *hamburger*, *menu de hamburger* ou *botão de hamburger*.) Você pode fixar o painel de navegação aberto ou ele pode ficar recolhido por padrão. Depois de fixar o painel de navegação aberto, o aplicativo o manterá aberto até que você o recolha.

## <a name="full-personalization-access-formerly-explicit-personalizations"></a>Acesso total à personalização (conhecido anteriormente como personalizações explícitas)

No nível de **acesso total à personalização**, os usuários têm acesso a todos os recursos de personalização no aplicativo. Como pessoas e empresas diferentes têm necessidades diferentes quando interagem com o aplicativo, especialmente em termos dos campos utilizados, a personalização fornece ferramentas que permitem que os usuários e as organizações personalizem a forma como as informações são organizadas e como interação com elas ocorre no aplicativo. Esses recursos são fundamentais para o fornecimento de experiências simplificadas e otimizadas nos aplicativos que são adaptados a você e à sua organização. 

Se o recurso [Exibições salvas](saved-views.md) estiver ativado, será necessário um salvamento explícito para que essas alterações persistam na experiência do usuário para uma exibição específica. Quando o recurso **Exibições salvas** está desativado, essas alterações são salvas automaticamente.

As seções a seguir abordam a extensão dos recursos de personalização que estão disponíveis para os usuários no nível de **acesso total à personalização**. Veja alguns dos recursos:

- Opções do menu de atalho
- A barra de ferramentas **Personalização**
- Adicionando blocos, listas e links a espaços de trabalho
- Como adicionar um resumo de um espaço de trabalho a um painel
- Personalizando o painel

### <a name="shortcut-menu-options"></a>Opções do menu de atalho

Os menus de atalho fornecem uma maneira de alterar a interface de uma página, de modo que ela atenda melhor aos seus requisitos ou às necessidades de sua organização. (Um menu de atalho também é conhecido como *menu do botão direito do mouse* ou *menu de contexto*.)

Algumas das alterações mais comuns e importantes a serem feitas em uma pagina estão disponíveis diretamente como opções em um menu de atalho. Por exemplo, se você quiser adicionar ou ocultar colunas em uma grade, basta clicar com o botão direito do mouse no cabeçalho de uma coluna e selecionar **Inserir colunas** ou **Ocultar esta coluna**.

Além disso, os tipos mais básicos de personalizações são disponibilizados clicando com o botão direito em um elemento e selecionando **Personalizar**. (Observe que nem todos os elementos na página podem ser personalizados.) Quando você usar esse método de personalização, a *janela de propriedades* do elemento será exibida.

![Personalização de propriedades de um elemento.](./media/cli-element-property-window.png)

Você pode usar a janela de propriedades para personalizar um elemento das seguintes maneiras:

- Alterar o rótulo do elemento.
- Ocultar o elemento para que ele não seja exibido na página. Os dados no campo não serão excluídos nem alterados. As informações não serão mais exibidas na página.
- Incluir as informações na seção de resumo da Guia Rápida (se o elemento estiver em uma Guia Rápida).
- Ignorar o campo, de forma que ele nunca receba o foco quando você percorrer a página usando a tecla Tab.
- Evitar que os dados no campo sejam editados (para qualquer registro).
- Designe um campo que será necessário para a entrada de dados. Se nenhum valor tiver sido inserido nesse campo, ele aparecerá com uma borda vermelha e um asterisco para indicar esse estado. Esta opção está disponível somente a partir da versão 10.0.11, quando os campos [Exibições salvas](saved-views.md) e **Designar campos como obrigatórios usando personalização** estão ativados.

A janela de propriedades pode incluir outros recursos de personalização, dependendo do elemento. Por exemplo, a janela de propriedades para um bloco pode permitir que você promova esse bloco para um painel, e as janelas de propriedades para elementos no painel padrão podem permitir que você crie um espaço de trabalho personalizado.

### <a name="personalization-toolbar"></a>Barra de ferramentas de personalização

Se quiser fazer várias alterações em uma página ou fazer alterações que não estejam disponíveis por meio de outros mecanismos (por exemplo, se você quiser reordenar elementos), você poderá usar a barra de ferramentas **Personalização**. Para abrir a barra de ferramentas **Personalização**, siga uma dessas etapas:

- Selecione **Ctrl + Shift + P** em qualquer elemento na página.
- Selecione **Personalizar esta página** na janela de propriedades de um elemento.
- Selecione **Personalizar esta página** no grupo **Personalizar** da guia **Opções** no Painel de Ação de qualquer página.
- Selecione o botão **Configurações** (símbolo de engrenagem) na barra de navegação e selecione **Personalizar**.

[![Barra de ferramentas de personalização.](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navegação na página

Quando a barra de ferramentas **Personalização** é aberta, a página subjacente é somente leitura (ou seja, você não pode editar os dados), mas ainda é interativa. Especificamente, é possível expandir ou recolher o painel **Informações relacionadas**, alternar guias e expandir ou recolher seções, da mesma maneira como você executaria normalmente essas ações na página. Para aplicar uma personalização a uma seção recolhível ou a uma guia (por exemplo, ocultar uma Guia Rápida), basta selecionar o botão exibido ao lado da seção ou da guia quando ela ganhar o foco do teclado ou quando você passar o mouse sobre ela.

#### <a name="personalization-tools"></a>Ferramentas de personalização

Estas ferramentas estão disponíveis na barra de ferramentas **Personalização**:

- Use a ferramenta **Selecionar** para selecionar e alterar as propriedades de um elemento. Para usar essa ferramenta, clique no botão **Selecionar** na barra de ferramentas e selecione o elemento desejado. A janela de propriedades do elemento será exibida, na qual você poderá modificar qualquer uma das propriedades desse elemento. Você pode repetir o processo para outros elementos que possam ser personalizados nessa página. Observe que algumas propriedades de personalização podem não estar disponíveis em alguns cenários. Por exemplo, não é possível bloquear um campo obrigatório.
- Use a ferramenta **Ocultar** para ocultar um elemento na página. Para usar essa ferramenta, selecione o botão **Ocultar** na barra de ferramentas e selecione o elemento a ser ocultado. Quando você usa a ferramenta **Ocultar**, todos os elementos que estiverem ocultos no momento ficarão visíveis, mas serão exibidos em um contêiner sombreado. Assim, você pode tornar um elemento visível selecionando-o. Para ver como a aparência da página quando os elementos estiverem ocultos, alterne para outra ferramenta de personalização ou feche a barra de ferramentas de personalização.
- Use a ferramenta **Adicionar campos** para adicionar campos à página. Ao usar esta ferramenta, você só poderá adicionar os campos que fazem parte da definição da página. Para obter informações sobre como criar novos campos que não fazem parte da definição de página atual, consulte [Criar e trabalhar com campos personalizados](user-defined-fields.md). Depois que selecionar o botão **Adicionar campos** na barra de ferramentas, você deverá primeiramente selecionar a grade ou a seção na qual deseja adicionar um campo. Uma caixa de diálogo exibirá a lista de campos relacionados à grade ou à seção selecionada. Na caixa de diálogo, selecione um ou mais campos para adicioná-los à lista **Campos recomendados** ou **Todos os campos**. Depois de escolher os campos desejados, selecione **Atualizar**. Para remover um campo adicionado anteriormente, repita o processo, mas desmarque a seleção do campo na caixa de diálogo.

    A lista **Campos recomendados** mostra os campos que foram adicionados anteriormente por outros usuários da organização. Esta lista de campos é atualizada com base na frequência de recorrência do **Trabalho em lotes de recomendação**. Uma experiência semelhante ocorre ao adicionar novos campos de filtro usando o painel Filtro em uma página.

- Use a ferramenta **Mover** para mover um elemento para um local diferente no grupo atual de elementos. Observe que não é possível mover um elemento para fora de seu grupo pai. Para usar essa ferramenta, selecione o botão **Mover** na barra de ferramentas e selecione o elemento a ser movido. Quando você seleciona um elemento, o aplicativo determina os locais para os quais o elemento pode ser movido. Esses locais são conhecidos como *zonas para soltar*. Quando você arrasta o elemento pelo grupo atual, cada zona para soltar é mostrada como uma linha colorida em negrito ao lado da área em que o elemento pode ser solto.
- Use a ferramenta **Ignorar** para remover um elemento da sequência de guias de teclado da página. Quando você seleciona o botão **Ignorar** na barra de ferramentas, todos os elementos ignorados no momento são exibidos em um contêiner sombreado. Você pode interativamente remover ou adicionar campos à sequência de guias.
- Use a ferramenta **Mostrar no cabeçalho** quando desejar que um campo seja exibido na seção de resumo da Guia Rápida. Quando você seleciona o botão **Mostrar no cabeçalho** na barra de ferramentas, todos os campos selecionados como campos de resumo são mostrados em um contêiner sombreado. É possível interativamente adicionar campos ao resumo da Guia Rápida e remover campos do resumo selecionando-os.
- Use a ferramenta **Requer** para designar um elemento conforme necessário para a entrada de dados. Quando você seleciona o botão **Exigir** na barra de ferramentas, todos os elementos personalizados como necessários são mostrados em um contêiner sombreado. Você pode torná-los desnecessários novamente. Esta opção está disponível na versão 10.0.12 e posteriores, quando o recurso **Designar campos como obrigatórios usando personalização** está habilitado.
- Use a ferramenta **Bloquear** para marcar um elemento como editável ou não editável. Quando você seleciona o botão **Bloquear** na barra de ferramentas, todos os elementos não editáveis no momento são exibidos em um contêiner sombreado. Você poderá torná-los editáveis novamente. Observe que alguns campos são obrigatórios e não podem ser alterados para não editáveis. Um símbolo de cadeado aparece ao lado desses campos.
- Use a ferramenta **Adicionar um aplicativo do Power Apps** para inserir na página um aplicativo criado usando o Microsoft Power Apps na página. Para obter informações detalhadas sobre como inserir um aplicativo do Power Apps em uma página, consulte [Inserir aplicativos do Power Apps](embed-power-apps.md). Esta opção está disponível somente quando o recurso [Exibições salvas](saved-views.md) estiver desativado.
- Use o botão **Adicionar um aplicativo** para inserir um aplicativo, criado do Microsoft Power Apps ou de terceiros, na página Esta opção está disponível somente quando o recurso [Exibições salvas](saved-views.md) estiver ativado. 
- Use a ferramenta **Limpar** para redefinir a página para o estado padrão instalado. Todas as personalizações na página atual serão limpas. Você não poderá desfazer essa ação. Portanto, use essa ferramenta somente se tiver certeza de que deseja redefinir a página. Quando o recurso **Exibições salvas** estiver ativado, essa ferramenta limpará as personalizações da exibição atual.
- Use a ferramenta **Importar** para carregar uma personalização de um arquivo que você ou outra pessoa criou anteriormente. 

    - Quando o recurso **Exibições salvas** estiver desativado, você poderá escolher se deseja adicionar ou substituir as personalizações existentes pelas personalizações que estão sendo importadas para a página. Você não poderá desfazer essa ação. Portanto, depois de importar as personalizações, você deve limpar ou desfazer manualmente todas as alterações que não desejar.
    - Quando o recurso **Exibições salvas** estiver ativado, as personalizações importadas se tornarão uma exibição na página. Se a exibição já existir, você terá a opção de ignorar a importação, substituir a exibição atual com o mesmo nome ou renomear a exibição importada.

- Use a ferramenta **Exportar** para salvar as personalizações da página em um arquivo. Em seguida, você poderá compartilhar as personalizações com outros usuários. Esses usuários só precisam importar o arquivo que contém as personalizações da página. Quando o recurso **Exibições salvas** estiver ativado, essa ferramenta salvará a exibição atual em um arquivo para compartilhamento.
- Selecione o botão **Fechar** para fechar a barra de ferramentas **Personalização** e retornar a página ao estado interativo anterior.

Tradicionalmente, quando a barra de ferramentas **Personalização** é usada, as personalizações entram em vigor assim que você as faz. Entretanto, se o recurso [Exibições salvas](saved-views.md) estiver ativado, você deverá salvar as personalizações explicitamente em uma exibição de sua preferência.

Em alguns casos, quando você seleciona uma ferramenta, aparece um símbolo de cadeado ao lado de um elemento. Esse símbolo indica que você não pode modificar as propriedades do elemento que estão relacionadas à ferramenta selecionada, pois as modificações nessas propriedades impedirão que a página funcione corretamente.

### <a name="adding-tiles-lists-and-links-to-a-workspace"></a>Adicionando blocos, listas e links a um espaço de trabalho

Para algumas páginas que incluem listas, o recurso de personalização **Adicionar ao espaço de trabalho** está disponível no grupo **Personalizar** da guia **Opções** no Painel de Ação. Esse recurso permite enviar por push as informações relevantes da lista atual para um espaço de trabalho específico. As informações exibidas no espaço de trabalho podem ser baseadas na lista inteira ou em uma versão classificada e filtrada da lista. Você também pode especificar se as informações aparecerão no espaço de trabalho como uma lista, um bloco resumido que pode mostrar o número de itens na lista ou um link.

> [!NOTE]
> Se o recurso [Exibições salvas](saved-views.md) estiver ativado, o conteúdo que você enviar por push para um espaço de trabalho será diretamente vinculado a uma exibição. A consulta da exibição é usada para recuperar dados no espaço de trabalho e o bloco ou link correspondente no espaço de trabalho abre a página nessa exibição, de modo que a consulta e as personalizações da exibição sejam aplicadas a ela. Se o modo de exibição for atualizado, os elementos correspondentes do espaço de trabalho serão ajustados para a nova definição de exibição.

[![Adicionar ao espaço de trabalho.](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Para adicionar uma lista a um espaço de trabalho, primeiro classifique ou filtre a lista na página de forma que ela mostre as informações como você deseja que apareçam no espaço de trabalho. (Se o recurso **Exibições salvas** estiver ativado, você não poderá prosseguir até salvar uma exibição com essas condições.) Em seguida, selecione **Adicionar ao espaço de trabalho**. Selecione um espaço de trabalho. No campo **Apresentação**, selecione **Lista**. Após você selecionar **Configurar**, aparecerá uma caixa de diálogo onde você poderá selecionar as colunas que devem aparecer na lista no espaço de trabalho. Você também pode especificar o rótulo usado para a lista no espaço de trabalho.
- Para adicionar um bloco a um espaço de trabalho, primeiramente filtre a lista na página para que ela mostre os dados que devem ser resumidos ou que você deseja acessar rapidamente. (Se o recurso **Exibições salvas** estiver ativado, você não poderá prosseguir até salvar uma exibição com essas condições.) Em seguida, selecione **Adicionar ao espaço de trabalho**. Selecione um espaço de trabalho. No campo **Apresentação**, selecione **Bloco**. Após selecionar **Configurar**,uma caixa de diálogo será exibida onde você poderá especificar o rótulo a ser usado para o bloco no espaço de trabalho. Você também pode especificar se o bloco deve mostrar uma contagem. Depois de ser adicionado ao espaço de trabalho, o bloco poderá ser selecionado para abrir a página atual no espaço de trabalho. Você pode, então, exibir a lista filtrada associada ao bloco.
- Para adicionar um link a um espaço de trabalho, primeiro filtre a lista na página para que ela mostre os dados do seu interesse. (Se o recurso **Exibições salvas** estiver ativado, você não poderá prosseguir até salvar uma exibição com essas condições.) Em seguida, selecione **Adicionar ao espaço de trabalho**. Selecione um espaço de trabalho. No campo **Apresentação**, selecione **Link**. Após selecionar **Configurar**, uma caixa de diálogo será exibida onde você poderá especificar o rótulo a ser usado para o link. Você também pode, opcionalmente, especificar um rótulo para a seção na qual este link pode ser colocado. Se essa seção não existir, uma nova seção será criada.

> [!NOTE]
> A partir da versão 10.0.25, quando você configura a lista, o bloco ou o link, também pode ser necessário selecionar os modos de exibição do espaço de trabalho aos quais você deseja adicionar o elemento, se o recurso **(Versão preliminar) Suporte de exibições salvas para espaços de trabalho** estiver habilitado. Os modos de exibição do espaço de trabalho disponíveis aparecerão na seção **Opções do espaço de trabalho** de cada caixa de diálogo **Configurar**. 

Após adicionar uma lista, um bloco ou um link a um espaço de trabalho, você pode abrir esse espaço de trabalho e reorganizar os elementos nele como desejar.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Como adicionar um resumo de um espaço de trabalho a um painel

Alguns espaços de trabalho contêm blocos de contagem (isto é, blocos com números). Talvez você deseje que esse blocos apareçam também no painel. Em um espaço de trabalho, clique com o botão direito do mouse em um bloco de contagem, selecione **Personalizar** e, em seguida, na janela de propriedades do bloco, selecione **Fixar no painel**. Na próxima vez que você abrir e atualizar o painel, a contagem será exibida abaixo do bloco de navegação desse espaço de trabalho. Você pode selecionar essa contagem para ir diretamente para os dados que ela representa.

### <a name="personalizing-your-dashboard"></a>Como personalizar seu painel

Geralmente, o painel é a primeira página que você vê ao abrir o aplicativo. Ele pode ser personalizado como qualquer outra página no sistema, usando-se os mesmos mecanismos descritos anteriormente neste tópico. 

> [!WARNING]
> No momento, quando você oculta o conteúdo no painel, é importante que você direcione diretamente um bloco, não o espaço ao redor dele. Se você ocultar o grupo ao redor de um bloco, pode haver resultados inesperados se mais blocos forem adicionados posteriormente ou se o sistema for alternado para um idioma diferente.

Um recurso de personalização exclusivo disponível no painel é a possibilidade de adicionar blocos. 

- Se o recurso **Aplicativos de página inteira** estiver desativado, você adicionará um novo bloco clicando com o botão direito do mouse em um elemento no painel e selecionando **Adicionar um espaço de trabalho**. Um novo bloco do espaço de trabalho será criado na parte inferior do painel. Você poderá renomear esse novo bloco do espaço de trabalho como desejar. Você também poderá adicionar listas, blocos e links ao espaço de trabalho, conforme descrito na seção [Adicionando blocos, listas e links a um espaço de trabalho](personalize-user-experience.md#adding-tiles-lists-and-links-to-a-workspace) deste tópico.
- Se o recurso **Aplicativos de página inteira** estiver ativado, você adicionará um novo bloco clicando com o botão direito do mouse em um elemento no painel e selecionando **Adicionar um aplicativo**. Na caixa de diálogo, selecione se você deseja adicionar um bloco para um novo espaço de trabalho ou um bloco que tenha conteúdo do Power Apps ou de um site. Em seguida, siga as etapas para configurar a opção selecionada. Um novo bloco será criado na parte inferior do painel. Para obter mais informações sobre como adicionar, editar, excluir e compartilhar esses aplicativos inseridos, consulte [Inserir aplicativos de tela do Power Apps](embed-power-apps.md) e [Inserir aplicativos de terceiros](embed-website.md).

## <a name="sharing-personalizations"></a>Como compartilhar personalizações

Após personalizar uma página, há alguns métodos que você pode usar para compartilhar as personalizações com outros usuários. Na lista a seguir, os métodos são organizados em ordem, do mais recomendável ao menos recomendado.

1. Publicar exibições para usuários.
2. Copiar exibições ou personalizações para usuários.
3. Exportar e importar exibições ou personalizações.

### <a name="publish-views-to-users"></a>Publicar exibições para usuários

Se o recurso [Exibições salvas](saved-views.md) estiver ativado e se a página der suporte a exibições, a melhor maneira de compartilhar personalizações com outros usuários é publicar a exibição para usuários com uma ou mais funções de segurança. Para obter mais informações, consulte [Publicar exibições](saved-views.md#publishing-views).

### <a name="copy-views-or-personalizations-to-users"></a>Copiar exibições ou personalizações para usuários

Se o recurso [Exibições salvas](saved-views.md) estiver desativado ou se a página não der suporte a exibições, a forma recomendável de compartilhar as personalizações será copiá-las entre usuários. Este método está disponível apenas para usuários privilegiados (por exemplo, administradores de sistema). Mas, os administradores podem procurar a personalização de um usuário específico no sistema (incluindo a exibição pessoal do usuário se as exibições salvas estiverem habilitadas) e copiar a configuração para outros usuários.

Se as exibições salvas estiverem habilitadas, siga estas etapas para copiar personalizações.

1. Acesse **Administração do sistema \> Configuração \> Personalização**.
2. Siga estas etapas para copiar exibições pessoais:

    1. Selecione **Exibições pessoais**.
    2. Selecione as exibições desejadas na lista.
    3. Selecione **Copiar para usuários**.
    4. Selecione os usuários para os quais as exibições serão distribuídas.

    Siga estas etapas para copiar personalizações em páginas que não dão suporte a exibições:

    1. Selecione **Configurações do usuário**.
    2. Selecione o usuário que tem a personalização a ser distribuída.
    3. Selecione **Gerenciar todas as personalizações**.
    4. Selecione as personalizações desejadas na lista.
    5. Selecione **Copiar para usuários**.
    6. Selecione os usuários para os quais as personalizações serão distribuídas.

Se as exibições salvas não estiverem habilitadas, siga estas etapas para copiar uma personalização.

1. Acesse **Administração do sistema \> Configuração \> Personalização**.
2. Selecione **Aplicar**.
3. Selecione os usuários para os quais a personalização será distribuída.
4. Selecione **Selecionar personalização existente**.
5. Localize e selecione a personalização (única) do seu interesse.
6. Selecione **OK**.

### <a name="export-and-import-views-or-personalizations"></a>Exportar e importar exibições ou personalizações

Outra maneira de compartilhar personalizações é por meio de exportação e importação. Os usuários individuais, ou um administrador que atua em seu nome, podem usar este método para exportar personalizações ou exibições e, depois, conceder o arquivo exportado a outros usuários para importação. Como alternativa, os usuários podem fornecer personalizações exportadas a um usuário com privilégios administrativos, e esse usuário pode usar a página de administração **Personalização** para aplicar o arquivo de personalização a vários usuários ao mesmo tempo.

> [!IMPORTANT]
> Como as personalizações são mantidas entre atualizações, a importação de todas as personalizações após uma atualização de serviço ou em qualquer outro momento é desnecessária e não recomendada.

#### <a name="export"></a>Exportar

Em geral, você pode exportar uma de suas próprias exibições ou personalizações, abrindo a página apropriada, abrindo a barra de ferramentas **Personalização** e selecionando **Exportar**. Para obter mais informações sobre a barra de ferramentas, consulte a seção [Barra de ferramentas Personalização](#personalization-toolbar) anteriormente neste tópico. Como alternativa, se as [exibições salvas](saved-views.md) estiverem habilitadas, você poderá acessar **Configurações \> Usar opções \> Personalização** para exibir uma lista de todas as suas personalizações no sistema. Deste ponto, você pode selecionar as exibições ou personalizações a serem exportadas e, depois, selecionar **Exportar**.

Além disso, os administradores podem exportar personalizações de outros usuários seguindo essas etapas.

1. Acesse **Administração do sistema \> Configuração \> Personalização**.
2. Na guia **Usuários**, selecione o usuário desejado.
3. Localize e selecione a exibição ou personalização do seu interesse.
4. Selecione **Exportar**.

#### <a name="import"></a>Importar

Para importar uma exibição ou personalização, basta abrir a barra de ferramentas **Personalização** e selecionar **Importar**. Além disso, os administradores podem importar um arquivo e logo fornecê-lo a um ou mais usuários.

Se as exibições salvas estiverem habilitadas, siga estas etapas.

1. Acesse **Administração do sistema \> Configuração \> Personalização**.
2. No Painel de Ações, selecione **Importar exibições \> Exibições de usuário**.
3. Selecione o modo de importação:

    - **Selecione usuários específicos** – conceda a exibição ou a personalização aos usuários selecionados.
    - **Importar como está** – importe a exibição ou a personalização para o mesmo usuário que a exportou.

4. Selecione **Navegar**, localize e selecione a personalização a ser importada.
5. Selecione **Avançar**.
6. Se você selecionou **Selecionar usuários específicos** na etapa 3, selecione os usuários para os quais a personalização será importada.
7. Selecione **Importar**.
8. Resolva os conflitos conforme necessário.

Se as exibições salvas não estiverem habilitadas, siga estas etapas.

1. Acesse **Administração do sistema \> Configuração \> Personalização**.
2. Selecione **Aplicar**.
3. Selecione os usuários para os quais a personalização será distribuída.
4. Selecione **Importar personalizações de um arquivo**.
5. Selecione **Navegar**, localize e selecione a personalização a ser importada.
6. Selecione **OK**.

## <a name="administration-of-personalizations"></a>Administração de personalizações

A página **Personalização** é o hub central para o gerenciamento de personalizações em um nível organizacional. O conteúdo e os recursos desta página dependem se o recurso **Exibições salvas** estiver ativado ou não.

Para os clientes que tenham o recurso **Exibições salvas** ativado, consulte a seção "Gerenciando exibições globalmente" no tópico [Exibições salvas](saved-views.md).

Para os clientes que ainda não ativaram o recurso [Exibições salvas](saved-views.md), essa página tem quatro guias:

- **Aplicar** – Você pode importar ou selecionar uma personalização de um ou mais usuários. Para aplicar uma personalização a um ou mais usuários, primeiro selecione uma função e os usuários que tenham essa função. Em seguida, selecione uma personalização existente para aplicar aos usuários selecionados ou importe um arquivo de personalização. A personalização será validada e aplicada a todos os usuários selecionados na próxima vez que eles abrirem a página selecionada.
- **Limpar** – você pode limpar todas as personalizações de uma página ou espaço de trabalho para um ou mais usuários. Primeiro, selecione uma página ou espaço de trabalho para ver uma lista de usuários que personalizaram essa página ou espaço de trabalho. Em seguida, selecione os usuários que devem ter as personalizações dessa página ou espaço de trabalho desmarcadas e selecione **Limpar**. Todas as personalizações que os usuários selecionados aplicaram à página ou ao espaço de trabalho selecionado serão excluídas. Essa ação não pode ser desfeita. Entretanto, se uma personalização tiver sido salva para a página ou o espaço de trabalho, essa personalização poderá ser reimportada.
- **Usuários** – Selecione um usuário para ver a lista de páginas que ele personalizou. Você pode habilitar ou desabilitar a capacidade de o usuário selecionado utilizar personalizações para páginas específicas ou para todo o sistema. Também é possível importar, exportar ou limpar uma personalização para o usuário. Além disso, você pode redefinir o recurso de textos explicativos para o usuário. Nesse caso, se o usuário tiver ignorado anteriormente qualquer janela pop-up que apresentava novos recursos, ela será exibida novamente na próxima vez que ele encontrar esses recursos.
- **Sistema** – É possível desativar temporariamente as personalizações de todos os usuários no sistema. Nesse caso, todas as personalizações são excluídas para todos os usuários e todas as páginas são redefinidos para seu estado padrão. Se, mais tarde, você ativar novamente a personalização, todas as personalizações serão reaplicadas. Também é possível excluir permanentemente todas as personalizações de todos os usuários do sistema. Não é possível recuperar as personalizações que foram excluídas. Portanto, antes de executar essa tarefa, verifique se você exportou todas as personalizações de que talvez precise posteriormente.

## <a name="personalizing-inventory-dimensions"></a>Personalizar dimensões de estoque

Quando você personalizar a configuração de dimensões de estoque em uma página, considere as configurações que foram criadas usando a opção **Dimensões de exibição**. Por exemplo, você usou a personalização para ocultar uma coluna para a dimensão de estoque do número de lote, mas a coluna aparecerá na próxima vez que a página for aberta. Esse comportamento ocorre porque as configurações **Exibição de dimensão** controlam as colunas de dimensão do estoque que são exibidas. As configurações de **Exibição de dimensão** se aplicam a todas as páginas e substituem qualquer configuração personalizada de campos de dimensão de estoque em páginas individuais.

Portanto, no exemplo anterior, se você não deseja que a coluna da dimensão de estoque do número de lote apareça na página, limpe essa dimensão como parte da opção **Exibir dimensões** dessa página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
