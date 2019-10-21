---
title: Personalizar a experiência do usuário
description: Este tópico explica como você pode personalizar o aplicativo.
author: jasongre
manager: AnnBe
ms.date: 06/11/2019
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
ms.openlocfilehash: edf698b12f2d0bcb6035bc644537cf9ca2bb87c9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190893"
---
# <a name="personalize-the-user-experience"></a>Personalizar a experiência do usuário

[!include [banner](../includes/banner.md)]

Este tópico explica como você pode personalizar o aplicativo.

Há três classes básicas de personalizações.

- Personalizações efetuadas em uma página de configuração. Os exemplos incluem um tema de cores e o fuso horário.
- Personalizações relacionadas ao uso da página, chamadas de *implícitas*. Por exemplo, o sistema controlará a largura das colunas de grade, se você ajustá-las, e o estado expandido ou recolhido das Guias Rápidas.
- Personalizações feitas por um usuário para modificar a aparência de uma página, alterando a maneira como um elemento aparece ou age nessa página. Isso costuma ser feito através de um modo de personalização interativo. Essas personalizações são chamadas de *explícitas*. Por exemplo, o usuário pode adicionar, ocultar ou reordenar elementos na página.

Cada personalização feita por um usuário destina-se somente a esse usuário, independentemente do tipo de personalização ou da empresa com a qual o usuário interage no momento. As alterações que um usuário faz em uma página não afetam outros usuários no sistema.

## <a name="system-wide-options-for-the-current-user"></a>Opções no nível do sistema para o usuário atual

A página **Opções do usuário** contém várias configurações do sistema para o usuário atual. Para abrir a página **Opções do usuário**, selecione o menu **Configurações** (o símbolo de engrenagem) na barra de navegação e, depois, **Opções do usuário**. A página **Opções do usuário** tem quatro guias que contêm várias configurações de usuário:

- **Visual** – selecione um tema de cores e o tamanho padrão de elementos nas páginas.
- **Preferências** – selecione os valores padrão que são usados sempre que você abre o sistema. Esses valores incluem a empresa, a página inicial e o modo de exibição/edição padrão. (O modo de exibição/edição determina se uma página está bloqueada para exibição ou aberta para edição sempre que ela é aberta.) Esta guia também inclui opções para o idioma, o fuso horário, além de data, tempo e formato numérico. Finalmente, esta guia inclui diversas preferências que variam de acordo com a versão.
- **Conta** – ajuste o nome do usuário e outras opções relacionadas à conta.
- **Fluxo de trabalho** – selecione opções relacionadas ao fluxo de trabalho.

Além de modificar as configurações de usuário, você também pode exibir e excluir dados de uso e personalizações clicando no botão **Dados de uso**. Quando você usa o aplicativo, muitas das seleções são lembradas para facilitar o uso do sistema no futuro. Especificamente, a guia **Personalização** permite exibir e gerenciar as alterações pessoais que você já fez nas páginas no sistema. Os textos explicativos de recursos, que são as janelas pop-up que apresentam os novos recursos do sistema (disponíveis na Atualização de plataforma 26), também podem ser redefinidos nesta guia para que você seja alertado novamente sobre recursos já encontrados.  

## <a name="implicit-personalizations"></a>Personalizações implícitas

As personalizações implícitas são aquelas que você executa ao interagir com controles que "reconhecem" seu estado de visibilidade atual.

- **Colunas de grade** – você pode ajustar a largura de uma coluna em uma grade ao selecionar a barra de dimensionamento à esquerda ou à direita do cabeçalho da coluna e deslizá-la para a esquerda ou a direita até a largura de coluna desejada. O aplicativo armazena a largura que você define para uma coluna. Ele redimensiona a coluna para essa largura sempre que você abre a página que inclui essa grade.
- **Guias Rápidas** – algumas páginas têm seções expansíveis conhecidas como *Guias Rápidas*. O aplicativo armazena informações sobre as Guias Rápidas que você expandiu e recolheu. Depois, sempre que você retornar à página, as mesmas Guias Rápidas serão expandidas ou recolhidas, com base em sua última interação com a página. Em alguns casos, você pode ajudar a melhorar o desempenho do sistema, recolhendo uma Guia Rápida, pois o aplicativo não precisa recuperar as informações dessa Guia Rápida até que ela seja expandida. Conforme explicado mais adiante neste tópico, também é possível alterar a ordem das Guias Rápidas em uma página.
- **Quadros de Fatos** – algumas páginas têm uma seção conhecida como *painel Quadro de Fatos*. Esse painel contém informações somente leitura que estão relacionadas ao assunto atual da página. Cada seção no painel Quadro de Fatos é conhecida como um *Quadro de Fatos*. Você pode ocultar ou mostrar o painel Quadro de Fatos inteiro. E também pode expandir ou recolher Quadros de Fatos individuais. O aplicativo armazena suas preferências. Depois, sempre que você retornar à página, o estado do painel Quadro de Fatos e de cada Quadro de Fatos individual será restaurado, com base em sua última interação com a página. Em alguns casos, você pode ajudar a melhorar o desempenho do sistema, recolhendo um Quadro de Fatos, pois o aplicativo não precisa recuperar as informações desse Quadro de Fatos até que ele seja expandido.
- **Painéis de ações** – um *Painel de ações* aparece na parte superior da maioria das páginas. O Painel de ações contém botões para muitas das ações que você pode executar na página atual. Esses botões costumam ser organizados em guias. É possível abrir o Painel de ações completo fixado ou deixá-lo recolhido por padrão. Na próxima vez que você abrir a página, o aplicativo restaurará o estado fixado do Painel de ações. Se o Painel de ações estiver aberto fixado, o aplicativo também mostrará a guia de ações usada por último.
- **Filtros Rápidos** – um *Filtro Rápido* aparecerá acima de muitas grades. O Filtro Rápido permite filtrar a grade, com base em uma coluna selecionada. O aplicativo armazena a coluna em que você filtrou. Da próxima vez que você abrir a página que inclui essa grade, a grade será filtrada na mesma coluna. Mas, você poderá filtrar na grade em uma coluna diferente.
- **Filtros do cabeçalho de coluna** – quando você filtrar uma grade usando *Filtros do cabeçalho de coluna*, poderá modificar o operador do filtro conforme necessário para localizar os dados desejados. Por exemplo, você pode alterar o operador de **inicia com** para **é exatamente**. Sempre que você usar um filtro de cabeçalho de coluna e alterar o operador de filtro, o aplicativo armazenará a alteração. Ele restaurará o operador de filtro na próxima vez em que você filtrar nessa coluna.
- **Painel de navegação** – é possível abrir o *Painel de navegação* selecionando o botão **Menu** no painel esquerdo de qualquer página. (O botão **Menu** às vezes é conhecido como *hamburger*, *menu de hamburger* ou *botão de hamburger*.) Você pode fixar o Painel de navegação como aberto ou pode recolhê-lo por padrão. Após você fixar o Painel de navegação como aberto, o aplicativo manterá esse painel aberto até você o recolher.

## <a name="explicit-personalizations"></a>Personalizações explícitas

A perspectiva de diferentes pessoas e empresas varia em relação aos dados que são mais importantes para elas, ou aos dados que não são necessários para a maneira como executam seus negócios. Você pode personalizar o modo como as informações são encomendadas e como você interage com elas. Você também pode especificar que algumas informações devam ser ocultas. Esses recursos são importantes para uma experiência pessoal e produtiva e são exemplos de personalizações explícitas. As personalizações explícitas são executadas explicitamente, visando alterar a aparência ou o comportamento de um elemento ou de uma página.

### <a name="shortcut-menu-options"></a>Opções do menu de atalho

Os menus de atalho fornecem algumas maneiras de alterar explicitamente uma página para melhor adequação aos seus requisitos ou às necessidades da sua empresa. (Um menu de atalho também é conhecido como *menu do botão direito do mouse* ou *menu de contexto*.)

Algumas das alterações mais comuns e importantes a serem feitas em uma pagina estão disponíveis diretamente como opções em um menu de atalho. Por exemplo, a partir da atualização de plataforma 17, para adicionar ou ocultar colunas em uma grade, basta clicar com o botão direito em um cabeçalho de coluna da grade e selecionar **Adicionar colunas** ou **Ocultar esta coluna**.

Além disso, para disponibilizar os tipos mais básicos de personalização explícita, clique com o botão direito em um elemento e selecione **Personalizar**. (Observe que nem todos os elementos na página podem ser personalizados.) Quando você usar esse método de personalização, aparecerá a janela de propriedades do elemento.

![Personalização de propriedades de um elemento](./media/personalization-element-properties.png)

Você pode usar a janela de propriedades para personalizar um elemento das seguintes maneiras:

- Alterar o rótulo do elemento.
- Ocultar o elemento para que ele não seja exibido na página. Os dados no campo não serão excluídos nem alterados. Apenas as informações não aparecerão mais na página.
- Incluir as informações na seção resumo da Guia Rápida (se o elemento estiver em uma Guia Rápida).
- Ignorar o campo quando você pressionar Tab para se movimentar entre os campos na página.
- Evitar que os dados no campo (para qualquer registro) sejam editados.

A janela de propriedades pode incluir outros recursos de personalização, dependendo do elemento. Por exemplo, a janela de propriedades para um bloco permitirá que você promova esse bloco para um painel. E a janela de propriedades para um painel permitirá que você crie um novo espaço de trabalho nesse painel.

### <a name="the-personalization-toolbar"></a>A barra de ferramentas de personalização

Se deseja fazer várias alterações em uma página ou fazer alterações que não estão disponíveis por meio de outros mecanismos (como a reorganização de elementos), use a barra de ferramentas **Personalização**. Para abrir a barra de ferramentas **Personalização**, selecione **Personalizar este formulário** na janela de propriedades de um elemento. Você também pode selecionar **Personalizar este formulário** no grupo **Personalizar** na guia **Opções** do Painel de Ação de cada página.

[![Barra de ferramentas de personalização](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navegação na página

A capacidade de navegar na página enquanto a **barra de ferramentas Personalização** estiver aberta depende da versão de plataforma que está em execução.

- Antes da atualização de plataforma 19, enquanto a barra de ferramentas **Personalização** está aberta, a página é somente leitura (nada pode ser inserido) e não interativa (alterações podem ser feitas somente nos elementos visíveis da página.) Se quiser fazer alterações nos elementos em uma seção recolhida ou em uma guia diferente, será necessário fechar a barra de ferramentas **Personalização** , expandir uma seção ou alternar para a guia desejada e abrir novamente a barra de ferramentas **Personalização** .

- A partir da atualização de plataforma 19, se a barra de ferramentas **Personalização** está aberta, a página é somente leitura, mas muito mais interativa. Especificamente, é possível expandir ou recolher o painel Quadro de Fatos, alternar guias e expandir ou recolher seções enquanto barra de ferramentas **Personalização** está aberta da mesma maneira que você realiza essas ações normalmente. Para aplicar uma alteração de personalização a uma seção recolhível ou a uma guia (por exemplo, para ocultar uma FastTab), você acionará o botão exibido ao lado da seção recolhível ou da guia quando ela ganhar o foco do teclado ou quando você passar o mouse sobre ela.

#### <a name="personalization-tools"></a>Ferramentas de personalização

Estas ferramentas estão disponíveis na barra de ferramentas **Personalização**:

- Use a ferramenta **Selecionar** para selecionar e alterar as propriedades de um elemento. Use a ferramenta **Selecionar** e, depois, selecione o elemento no qual deseja modificar as propriedades. Quando você selecionar um elemento, a janela de propriedades do elemento aparecerá e você poderá modificar qualquer propriedade desse elemento. Você pode repetir o processo para outros elementos que possam ser personalizados nessa página. Entretanto, devido à forma como alguns elementos são usados, o aplicativo não permitirá alterar algumas das propriedades. Portanto, ao selecionar um elemento, note que algumas das propriedades não podem ser modificadas. Por exemplo, você não pode ocultar um campo obrigatório.
- Use a ferramenta **Mover** para mover um elemento para um local diferente no grupo atual de elementos. (Você não pode mover um elemento para fora de seu grupo pai). Selecione a ferramenta **Mover** e, depois, o elemento a ser movido. Quando você seleciona um elemento, o aplicativo verifica a página para determinar onde o elemento pode ser movido. Depois, ele cria uma série de “zonas para soltar”. Quando você arrasta o elemento no grupo atual, cada “zona para soltar” é mostrada como uma linha colorida em negrito ao lado da área em que o elemento pode ser solto.
- Use a ferramenta **Ocultar** para ocultar um elemento na página. Selecione a ferramenta **Ocultar** e, depois, o elemento a ser oculto. Quando você seleciona a ferramenta **Ocultar**, todos os elementos ocultos no momento ficam visíveis e são exibidos em um contêiner sombreado. Você poderá reexibi-los. Ao selecionar a ferramenta **Selecionar**, você pode ver a aparência da página quando os elementos selecionados ficam ocultos.

    - A partir da atualização de plataforma 18, você pode ocultar os campos e seções obrigatórios que contêm campos obrigatórios. Isso permite criar uma experiência simplificada em que os campos necessários definidos como padrão pela lógica comercial não são mostrados. Os campos obrigatórios ocultados também ficam temporariamente visíveis se estiverem vazios ao tentar salvá-los.

- Use a ferramenta **Resumo** quando desejar que um elemento apareça na seção resumo da Guia Rápida. A ferramenta Resumo se aplica somente aos campos contidos em uma seção resumo da Guia Rápida. Quando você seleciona a ferramenta **Resumo**, todos os campos selecionados como campos resumidos são mostrados em um contêiner sombreado. Você pode interativamente adicionar campos ao resumo da Guia Rápida. Para remover campos do resumo da Guia Rápida, selecione os campos.
- Use a ferramenta **Ignorar** para remover um elemento da sequência de guias de teclado da página. Quando você seleciona a ferramenta **Ignorar**, todos os elementos ignorados no momento são exibidos em um contêiner sombreado. Você poderá torná-los parte da sequência de guias novamente.
- Use a ferramenta **Editar** para marcar um elemento como editável ou não editável. Quando você seleciona a ferramenta **Editar**, todos os elementos não editáveis no momento são mostrados em um contêiner sombreado. Você poderá torná-los editáveis novamente. Observe que alguns campos são obrigatórios e não podem se tornar não editáveis. Um símbolo de cadeado aparece ao lado desses campos.
- Use o botão **Inserir** para ver uma lista de elementos que podem ser inseridos em uma página.

    - Selecione a ferramenta **Campo** em **Inserir** para adicionar um campo à página. Ao usar a ferramenta **Campo**, você poderá adicionar somente os campos que fazem parte da definição de página, mas que não aparecem na página no momento. Para obter informações sobre como criar novos campos que não fazem parte da definição de página atual, consulte [Campos personalizados](user-defined-fields.md). Após selecionar a ferramenta **Campo**, primeiro selecione o grupo ou a área em que você deseja adicionar um campo. Uma caixa de diálogo mostrará a lista de campos relacionados ao grupo ou área selecionada. Na caixa de diálogo, escolha um ou mais campos a serem adicionados e selecione **Inserir**. Para remover um campo adicionado anteriormente, repita o processo, mas desmarque a seleção do campo na caixa de diálogo.
    - Selecione a ferramenta **PowerApp** em **Inserir** para inserir um aplicativo criado usando o Microsoft PowerApps na página. Para obter informações detalhadas sobre como incorporar um aplicativo PowerApps em uma página, consulte [Incorporar PowerApps](embed-power-apps.md).

- Selecione o botão **Gerenciar** para exibir uma lista de opções de gerenciamento relacionadas a todas personalizações da página atual.

    - Selecione **Limpar** para redefinir a página com seu padrão, o estado instalado. Todas as personalizações na página atual serão apagadas. Não é possível desfaz a ação. Portanto, use esta opção somente se tiver certeza de que deseja redefinir a página.
    - Selecione **Importar** para carregar a personalização de um arquivo que você ou outra pessoa criou previamente para a página. Todas as personalizações atuais da página são substituídas pelas personalizações do arquivo selecionado.
    - Selecione **Exportar** para salvar as personalizações da página em um arquivo. Você pode compartilhar as personalizações com outros usuários. Esses usuários só precisam importar o arquivo que contém as personalizações da página.

- Selecione o botão **Fechar** para fechar a barra de ferramentas **Personalização** e retornar a página ao estado interativo anterior.

Quando a barra de ferramentas **Personalização** for usada, as operações de salvamento serão implícitas. As personalizações entrarão em vigor assim que você criá-las. Não é necessário selecionar um botão **Salvar**. Em alguns casos, quando você seleciona uma ferramenta, aparece um símbolo de cadeado ao lado de um elemento. Esse símbolo indica que você não pode modificar as propriedades do elemento que estão relacionadas à ferramenta selecionada, pois as modificações nessas propriedades impedirão que a página funcione corretamente.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Como adicionar um bloco, uma lista ou um link a um espaço de trabalho

Para algumas páginas com listas, há um recurso de personalização adicional disponível. O botão **Adicionar ao espaço de trabalho** no grupo **Personalizar** na guia **Opções** do Painel de ações permite que você mostre as informações da lista atual em um espaço de trabalho específico. Você pode mostrar uma exibição filtrada e classificada das informações no espaço de trabalho ou pode mostrar a exibição padrão. Você também pode especificar se as informações aparecerão no espaço de trabalho como uma lista, como um bloco resumido que pode mostrar o número de itens na lista ou como um link.

[![Adicionar ao espaço de trabalho](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Para adicionar uma lista a um espaço de trabalho, primeiro classifique ou filtre a lista na página de forma que ela mostre as informações como você deseja que apareçam no espaço de trabalho. Selecione **Adicionar ao espaço de trabalho**. Selecione um espaço de trabalho. No campo **Apresentação**, selecione **Lista**. Após você selecionar **Configurar**, aparecerá uma caixa de diálogo onde você poderá selecionar as colunas que devem aparecer na lista no espaço de trabalho. Você também pode especificar o rótulo a ser usado para a lista no espaço de trabalho.
- Para adicionar um bloco a um espaço de trabalho, primeiro filtre a lista na página para que ela mostre os dados a serem resumidos ou que você deseja acessar rapidamente. Selecione **Adicionar ao espaço de trabalho**. Selecione um espaço de trabalho. No campo **Apresentação**, selecione **Bloco**. Após você selecionar **Configurar**, aparecerá uma caixa de diálogo onde você poderá especificar o rótulo a ser usado para um bloco no espaço de trabalho. Você também pode especificar se o bloco deve mostrar uma contagem. Após o bloco ser adicionado ao espaço de trabalho, você poderá selecioná-lo para abrir a página atual a partir do espaço de trabalho e exibir a lista filtrada associada ao bloco.
- Para adicionar um link a um espaço de trabalho, primeiro filtre a lista na página para que ela mostre os dados do seu interesse. Selecione **Adicionar ao espaço de trabalho**. Selecione um espaço de trabalho. No campo **Apresentação**, selecione **Link**. Após você selecionar **Configurar**, aparecerá uma caixa de diálogo onde você poderá especificar o rótulo a ser usado para o link. Você também pode, opcionalmente, especificar um rótulo para uma nova seção que conterá esse link.

Após adicionar a lista, o bloco ou o link a um espaço de trabalho, você poderá abrir esse espaço de trabalho e reordenar os elementos nele como desejar.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Como adicionar um resumo de um espaço de trabalho a um painel

Alguns espaços de trabalho contêm blocos de contagem (isto é, blocos com números). Talvez você deseje que esse blocos apareçam também no painel. Em um espaço de trabalho, clique com o botão direito em um bloco de contagem e selecione **Personalizar**. Em seguida, na janela de propriedades do bloco, selecione **Fixar no painel**. Na próxima vez que você abrir (e atualizar) o painel selecionado, a contagem aparecerá abaixo do bloco de navegação para esse espaço de trabalho. Você pode selecionar essa contagem para ir diretamente para os dados que ela representa.

### <a name="personalizing-your-dashboard"></a>Como personalizar seu painel

Geralmente, o painel é a primeira página que você vê ao abrir o aplicativo. É possível personalizar o painel de forma que ele mostre apenas os blocos do espaço de trabalho que você deseja ver. Você também pode reorganizar os blocos na ordem que você preferir, renomear os blocos de navegação do espaço de trabalho ou adicionar um bloco de espaço de trabalho totalmente novo.

Para personalizar o painel, clique com o botão direito no bloco e selecione **Personalizar** para abrir a janela de propriedades do bloco.

- Se desejar ocultar ou renomear o bloco selecionado, você poderá fazer essa alteração diretamente na janela de propriedades.
- Para reordenar os blocos do espaço de trabalho, na janela de propriedades, selecione **Personalizar este formulário** para abrir a barra de ferramentas **Personalização**. Você poderá usar a ferramenta **Mover** para organizar os blocos como desejar.
- Para criar um novo bloco do espaço de trabalho, na janela de propriedades, selecione **Adicionar um espaço de trabalho**. Um novo bloco do espaço de trabalho será criado na parte inferior do painel. Você poderá renomear esse novo bloco do espaço de trabalho como desejar. Você também pode adicionar listas, blocos e links ao espaço de trabalho, conforme descrito na seção [Como adicionar listas, blocos e links a espaços de trabalho](personalize-user-experience.md#adding-a-tile-list-or-link-to-a-workspace) deste tópico.

## <a name="administration-of-personalization"></a>Administração de personalização

Após personalizar uma página, você pode compartilhar as personalizações com outros usuários exportando a página personalizada. Você pode solicitar que outros usuários abram a página personalizada e importem o arquivo personalização que você criou. Outra opção é conceder sua personalização a um usuário que tenha privilégios de administrador. Esse usuário poderá aplicar seu arquivo de personalização a vários usuários ao mesmo tempo.

Os usuários com privilégios de administrador também podem gerenciar personalizações para outros usuários na página **Personalização**. Essa página tem quatro guias:

- **Aplicar** – Você pode importar ou selecionar uma personalização de um ou mais usuários. Para aplicar uma personalização a um ou mais usuários, primeiro selecione uma função e os usuários que tenham essa função. Em seguida, selecione uma personalização existente para aplicar aos usuários selecionados ou importe um arquivo de personalização. A personalização será validada e aplicada a todos os usuários selecionados na próxima vez que eles abrirem a página selecionada.
- **Limpar** – você pode limpar todas as personalizações de uma página ou espaço de trabalho para um ou mais usuários. Primeiro, selecione uma página ou espaço de trabalho para ver uma lista de usuários que personalizaram essa página ou espaço de trabalho. Em seguida, selecione os usuários que devem ter as personalizações dessa página ou espaço de trabalho desmarcadas e selecione **Limpar**. Todas as personalizações que os usuários selecionados aplicaram à página ou ao espaço de trabalho selecionado serão excluídas. Essa ação não pode ser desfeita. Entretanto, se uma personalização tiver sido salva para a página ou o espaço de trabalho, essa personalização poderá ser reimportada.
- **Gerenciador por usuário** – selecione um usuário para ver a lista de páginas que ele personalizou. Você pode habilitar ou desabilitar a capacidade de o usuário selecionado utilizar personalizações para páginas específicas ou para o sistema inteiro. Também é possível importar, exportar ou limpar uma personalização para o usuário selecionado. Além disso, você pode redefinir os textos explicativos de recursos para o usuário selecionado, assim todas as janelas pop-up anteriormente ignoradas que apresentavam os novos recursos serão novamente exibidas na próxima vez que o usuário encontrá-los.   
- **Sistema** – É possível desativar temporariamente todas as personalizações de todos os usuários do sistema. Nesse caso, as personalizações serão excluídas. Todas as páginas são redefinidas com o estado padrão para todos os usuários. Se, mais tarde, você habilitar novamente a personalização, todas as personalizações serão reaplicadas. Também é possível excluir permanentemente todas as personalizações de todos os usuários do sistema. Não é possível recuperar personalizações que foram excluídas. Portanto, antes de executar essa tarefa, verifique se você exportou todas as personalizações de que talvez precise posteriormente.

## <a name="personalization-of-inventory-dimensions"></a>Personalização das dimensões de estoque

Quando você personalizar a configuração de dimensões de estoque em uma página, considere as configurações que foram criadas usando a opção **Dimensões de exibição**. Por exemplo, você usou a personalização para ocultar uma coluna para a dimensão de estoque do número de lote, mas a coluna aparecerá na próxima vez que a página for aberta. Esse comportamento ocorre porque as configurações **Exibição de dimensão** controlam as colunas de dimensão do estoque que são exibidas.

As configurações de **Exibição de dimensão** aplicam-se a todas as páginas e substituem a configuração personalizada de campos de dimensão de estoque em cada página individual.

Como resultado, no exemplo anterior, se você não deseja que a coluna da dimensão de estoque do número de lote apareça na página, limpe essa dimensão como parte da opção **Exibir dimensões** dessa página.
