---
title: "Personalizar a experiência do usuário"
description: "Este tópico explica como é possível personalizar o Microsoft Dynamics 365 for Finance and Operations."
author: TLeforMicrosoft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7a828090fa34eb96d2b557eb06e48ad05b421ae8
ms.openlocfilehash: 3d969069dd5f447b449df84b097527d3814aa338
ms.contentlocale: pt-br
ms.lasthandoff: 11/20/2017

---

# <a name="personalize-the-user-experience"></a>Personalizar a experiência do usuário

[!include [banner](../includes/banner.md)]

Este tópico explica como é possível personalizar o Microsoft Dynamics 365 for Finance and Operations.

Há vários tipos de personalizações no Dynamics 365 for Finance and Operations. Algumas personalizações são as seleções feitas em uma lista de opções em uma página de configuração. Algumas personalizações são implícitas, por exemplo, o Finance and Operations controla as larguras das colunas de grade se você ajustá-las e o estado expandido/recolhido das Guias Rápidas. Outras personalizações são explícitas. Para personalizações explícitas, você entra em um modo de personalização interativo e modifica a aparência de uma página ao gerenciar diretamente a forma como esses elementos aparecerão ou atuarão na página. 

Qualquer tipo de personalização feita por um usuário no Finance and Operations destina-se somente a esse usuário, independentemente da empresa com a qual o usuário interage. As alterações que um usuário faz em uma página não afetam outros usuários no sistema.

## <a name="system-wide-options-for-the-current-user"></a>Opções no nível do sistema para o usuário atual
Na barra de navegação, você encontrará a imagem de uma engrenagem, que é o botão de menu **Configurações**. Ao abrir o menu **Configurações**, você verá uma série de opções. Selecionar **Opções** abrirá a página **Opções** do usuário. Ali, você encontrará quatro guias de opções: 

-   **Visual:** – use-a para escolher um tema de cor e o tamanho padrão dos elementos nas páginas.
-   **Preferências:** – aqui você pode escolher padrões cada vez que abrir o Finance and Operations, incluindo a empresa, a página inicial e o modo de exibição/edição padrão (que determina se uma página será bloqueada para exibição ou aberta para edição cada vez que for aberta). Você também encontrará opções de idioma, fuso horário, data, hora e formato de número. Por fim, esta página contém preferências diversas que variarão de acordo com a versão.
-   **Conta:** – use para fornecer a ID do usuário e outras opções relacionadas à conta.
-   **Fluxo de trabalho:** – aqui é possível escolher opções relacionadas ao fluxo de trabalho.

## <a name="implicit-personalizations"></a>Personalizações implícitas
As personalizações implícitas são aquelas que você executa ao interagir com alguns controles que reconhecem seu estado de visibilidade atual. 

- **Colunas de grade:** – você pode ajustar a largura de uma coluna em uma lista ao selecionar a barra de dimensionamento à esquerda ou à direita do cabeçalho da coluna e deslizá-la para esquerda ou direita até a largura desejada. O Finance and Operations armazenará a largura de sua preferência e exibirá essa coluna com essa largura todas as vezes que você abrir a página com essa lista. 

- **Guias Rápidas** - algumas páginas têm seções expansíveis chamadas *Guias Rápidas*. O Finance and Operations armazenará as Guias Rápidas que você expandiu e as Guias Rápidas que você recolheu. Cada vez que você retornar à página, as mesmas Guias Rápidas estarão expandidas ou recolhidas, com base na sua última utilização. Neste artigo, explicaremos como alterar a ordem das seções das Guias Rápidas. Em alguns casos, recolher uma Guia Rápida pode melhorar o desempenho, pois o Finance and Operations não precisará recuperar as informações dessa Guia Rápida até que ela seja expandida. 

- **Quadros de Fatos** - algumas páginas têm uma seção chamada painel de *Quadros de Fatos*. Esse painel contém informações somente leitura relacionadas ao assunto atual da página. Cada seção no painel Quadro de Fatos é chamada de Quadro de Fatos. Você pode expandir ou recolher um Quadro de Fatos e o Finance and Operations armazenará sua preferência. Em alguns casos, recolher um Quadro de Fatos pode melhorar o desempenho, pois o Finance and Operations não precisará recuperar as informações desse Quadro de Fatos até que ele seja expandido.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Personalizações explícitas usando a barra de ferramentas Personalização
Cada pessoa e empresa têm uma perspectiva diferente de quais dados são mais importantes ou quais dados não são necessários para a maneira como eles conduzem seus negócios. A capacidade de personalizar a maneira como você organiza as informações, interage ou até mesmo oculta suas informações é a chave para tornar o Finance and Operations uma experiência pessoal e produtiva. 

As personalizações explícitas são aquelas executadas explicitamente com a intenção de alterar a aparência ou comportamento de um elemento ou de uma página, escolhendo a partir de um menu de personalização. O tipo mais básico de personalização explícita é quando você clica co o botão direito em um elemento e seleciona **Personalizar**. (Observe que nem todos os elementos na página podem ser personalizados.) Quando você seleciona esse método de personalização, verá a janela de propriedades do elemento. 

[![Personalizando propriedades de um elemento](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg) 

Você personalizará um elemento na página dessa maneira se quiser apenas alterar o rótulo do elemento, ocultar o elemento para que ele não seja exibido na página (isso não altera nenhum dado, isso simplesmente não exibe a informação), incluir as informações na seção de resumo da Guia Rápida (se o elemento estiver em uma Guia Rápida), ignorar o campo ao usar a tabulação ou fazer isso para que os dados não possam ser alterados por meio da marcação “Não Editar.” 

Para mover ou ocultar elementos ou fazer várias alterações, use a barra de ferramentas Personalização, disponível na janela de Propriedade dos elementos quando você escolhe **Personalize este formulário**. A barra de ferramentas Personalização também está disponível no painel de Ação do formulário, no grupo **Personalizar** da guia **Opções**. Selecione **Personalizar este formulário** e você verá a barra de ferramentas Personalização. 

[![Barra de ferramentas de personalização](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

A barra de ferramentas Personalização tem uma série de ações de personalização. 

- Escolha a ferramenta **Selecionar** para selecionar e alterar as propriedades de vários elementos, um de cada vez. Primeiro, clique na ferramenta Selecionar e, depois, clique no elemento cujas propriedades você deseja modificar. Ao selecionar um elemento, a janela de propriedades do elemento será aberta e você poderá modificar qualquer propriedade desse elemento. Você pode repetir o processo para outros elementos personalizáveis no formulário. Em alguns casos, você selecionará um elemento e perceberá que algumas propriedades não são modificáveis. Isso significa que, com base na forma como o elemento atual é usado, o Finance and Operations não permite alterar essa propriedade. Por exemplo, você não pode ocultar um campo obrigatório. 

- Escolha a ferramenta **Mover** quando quiser selecionar e mover um elemento para um local diferente no grupo atual de elementos. (Você não pode mover um elemento para fora de seu grupo pai). Primeiro, clique na ferramenta Mover e, em seguida, clique no elemento que deseja mover. Quando você clica no elemento a ser movido, o Finance and Operations verifica o formulário para determinar para onde esse elemento pode ser movido e cria uma série de "zonas para soltar" que são exibidas como uma linha colorida em negrito, ao lado da área em que o elemento pode ser solto, enquanto você arrasta o elemento para dentro do grupo atual. 

- Escolha a ferramenta **Ocultar** para selecionar e ocultar um elemento. Para ocultar um elemento, basta escolher a ferramenta Ocultar e clicar no elemento que você deseja ocultar. Quando você escolher a ferramenta Ocultar, todos os elementos ocultos atuais ficarão visíveis e serão exibidos em um contêiner sombreado, para que você possa escolher o elemento que será reexibido. 

- Escolha a ferramenta **Selecionar** para ver a aparência da página com os elementos ocultos selecionados. 

- Escolha a ferramenta **Resumo** quando quiser que um campo numérico ou de cadeia de caracteres seja exibido na área de resumo da Guia Rápida. A ferramenta Resumo se aplicará somente a campos que estejam contidos em uma seção de Guia Rápida. Quando você escolhe a ferramenta Resumo, o Finance and Operations exibe todos os campos que foram selecionados como campos de resumo, colocando-os em um contêiner sombreado. Você pode adicionar e remover interativamente campos de um resumo da Guia Rápida clicando no campo. 

- Escolha a ferramenta **Ignorar** para remover um elemento da sequência de guias de teclado da página. Quando você escolher a ferramenta Ignorar, todos os elementos atualmente ignorados serão exibidos em um contêiner sombreado, para que você possa escolhê-los novamente e torná-los parte da sequência de guias. 

- Escolha a ferramenta **Editar** quando quiser marcar um elemento como *Editável* ou *Não editável*. Quando você escolhe a ferramenta Editar, todos os elementos não editáveis atuais são exibidos em um contêiner sombreado, para que você possa escolhê-los para torná-los editáveis. Observe que alguns campos são obrigatórios e não podem se tornar não editáveis. Esses campos aparecerão com um ícone de cadeado. 

- Escolha a ferramenta **Adicionar** para adicionar um campo à página. Com a ferramenta Adicionar, não é possível criar um campo novo, mas você pode adicionar campos que já fazem parte da definição de página atual e não estão exibidos na página. Ao escolher a ferramenta Adicionar, você precisará primeiro selecionar o grupo ou a área ao qual deseja adicionar um campo. Uma caixa de diálogo exibirá a lista de campos relacionados à seção que você selecionou. Nessa caixa de diálogo, você pode selecionar um ou mais campos a serem adicionados e clicar em **Inserir**. Se, posteriormente, você desejar remover um campo já adicionado, repita o processo, mas apenas limpe o campo que adicionou. 

- Escolha o botão **Gerenciar** para ver uma lista de opções de gerenciamento relacionada a todas personalizações da página atual. 

- Escolha **Limpar** para redefinir a página a seu padrão, estado instalado. Todas as personalizações na página atual serão limpas. Não há ação para desfazer, então use apenas essa opção quanto estiver certo que deseja redefinir sua página. 

- Escolha **Importar** para usar a personalização de um arquivo de personalização que você ou outra pessoa criaram previamente para essa página. Importar uma personalização removerá todas as personalizações existentes na página e usará todas as personalizações do arquivo selecionado. Se você quiser salvar ou compartilhar uma personalização, selecione a opção **Exportar** para salvar as personalizações em um arquivo. 

- Escolha o botão **Fechar** para fechar a barra de ferramentas e retornar a página ao seu estado interativo anterior. 

Com a barra de ferramentas Personalização, o salvamento é implícito. As personalizações são efetuadas imediatamente; não é necessário clicar no botão **Salvar**. Em alguns casos, você verá um ícone de cadeado próximo a um elemento quando selecionar uma ferramenta. Isso significa que, para que a página funcione corretamente, você não pode modificar as propriedades relacionadas à ferramenta selecionada. Quando a barra de ferramentas Personalização for aberta, a página se tornará não interativa. Você não pode inserir dados nem expandir ou recolher seções.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Personalização explícita: Adicionando um bloco ou uma lista a um espaço de trabalho
Algumas páginas com listas terão um recurso adicional de personalização disponível no Painel de Ação, no grupo **Personalizar** da guia **Opções**. Selecione **Adicionar ao Espaço de Trabalho** para abrir a lista suspensa que permite exibir as informações da lista atual (filtrada e classificada ou padrão) em um espaço de trabalho como uma lista ou bloco resumido (que pode ser usado para exibir o número de itens na lista). 

[![Adicionar ao espaço de trabalho](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Para adicionar uma lista a um espaço de trabalho, primeiro classifique ou filtre a lista com as informações que você deseja ver em seu espaço de trabalho e, em seguida, marque a caixa de diálogo **Adicionar ao Espaço de Trabalho**. Em seguida, selecione o espaço de trabalho desejado e selecione **Lista** na lista suspensa **Apresentação**. Quando você selecionar **Lista**, uma caixa de diálogo será aberta, permitindo que você escolha as colunas que deseja ver na lista, e o rótulo da lista, conforme é exibido no espaço de trabalho. 

Para adicionar um bloco a um espaço de trabalho, primeiro filtre a lista para representar os dados que você deseja resumir (ou deseja acessar rapidamente). Em seguida, abra a caixa de diálogo suspensa **Adicionar ao Espaço de Trabalho**. Depois, selecione o espaço de trabalho desejado e selecione **Bloco** do menu suspenso **Apresentação**. Quando você selecionar **Bloco**, uma caixa de diálogo será aberta, permitindo que você forneça um rótulo de bloco e decida se o bloco exibirá uma contagem. Quando inserido em um espaço de trabalho, o bloco permitirá que você abra a página atual do espaço de trabalho e exiba a lista de informações relacionadas ao bloco. 

Quando a lista ou o bloco é adicionado a um espaço de trabalho, você pode abrir esse espaço de trabalho e reordenar a lista ou o bloco no grupo em que ele foi inserido.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Personalização explícita: Adicionando um resumo de um espaço de trabalho a um painel
Alguns espaços de trabalho contém os blocos de contagem (blocos com números neles) que você também gostaria de ver no painel. Em um espaço de trabalho, clique com o botão direito em um quadro de contagem, selecione **Personalizar** e, em seguida, selecione **Fixar no Painel**. Na próxima vez que você navegar para (e atualizar) o painel selecionado, verá essa contagem abaixo do bloco de navegação do espaço de trabalho no painel.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Personalização explícita: Personalizando o painel
Geralmente, o painel é a primeira página que você vê quando abre o Finance and Operations. Você pode personalizar o painel para renomear os blocos de navegação do espaço de trabalho, exibir somente os blocos desejados, renomear os blocos ou organizar os blocos na ordem em que você preferir consultá-los. 

Para personalizar o painel, selecione qualquer bloco e clique com o botão direito do mouse para abrir um menu de contexto. No menu de contexto, selecione **Personalizar**. Se o bloco selecionado for o que você deseja ocultar, renomear ou ignorar, faça essa alteração diretamente na janela Propriedade exibida. Para organizar os blocos, selecione **Personalizar este formulário** na janela Propriedade para abrir a barra de ferramentas Personalização. Você pode usar a ferramenta **Mover** para organizar os blocos.

## <a name="administration-of-personalization"></a>Administração de personalização
Após personalizar uma página, você pode compartilhar as personalizações com outros usuários exportando a página personalizada. Em seguida, você poderá solicitar que os outros usuários naveguem até a página personalizada e importem o arquivo de personalização criado, ou você pode dar sua personalização a um usuário com os privilégios administrativos, que poderá então aplicar seu arquivo de personalização a vários usuários ao mesmo tempo.

Os usuários com privilégios de administrador também podem gerenciar personalizações para outros usuários na página **Personalização**. Essa página tem quatro guias: 

- **Aplicar** – Você pode importar ou selecionar uma personalização de um ou mais usuários. Para aplicar uma personalização a um ou mais usuários, selecione uma função e usuários dentro dessa função, depois selecione uma personalização existente ou importe um arquivo de personalização para aplicar aos usuários selecionados. A personalização será validada e aplicada a todos os usuários selecionados na próxima vez que eles abrirem a página selecionada.

- **Limpar** – Você pode limpar as personalizações da página ou do espaço de trabalho para um ou mais usuários. Selecione uma página para consultar a lista de usuários que personalizaram essa página. Em seguida, selecione os usuários que devem ter as personalizações dessa página desmarcadas e selecione **Limpar**. Todas as personalizações que os usuários selecionados aplicaram para a página ou o espaço de trabalho selecionado serão apagadas. Essa ação não pode ser desfeita. Entretanto, se a página ou o espaço de trabalho tem uma personalização salva, essa personalização pode ser reimportada.

- **Gerenciador por Usuário** – Escolha um usuário para ver a lista de páginas que esta pessoa personalizou.  Você pode optar por habilitar ou desabilitar sua capacidade de utilizar a personalização de páginas específicas ou do sistema inteiro.  Também é possível importar, exportar ou limpar uma personalização deste usuário.

- **Sistema** – É possível desativar temporariamente todas as personalizações de todos os usuários do sistema. Fazer isso, não excluirá as personalizações, mas simplesmente redefinirá todas as páginas ao estado padrão, para todos os usuários. Se, mais tarde, você habilitar novamente a personalização, todas as personalizações serão reaplicadas. Também é possível excluir permanentemente todas as personalizações de todos os usuários do sistema. Certifique-se de exportar todas as personalizações que talvez você queira posteriormente, antes de executar esta etapa, pois não há como recuperar personalizações excluídas posteriormente. 

## <a name="personalization-of-inventory-dimensions"></a>Personalização das dimensões de estoque

Quando você personalizar a configuração de dimensões de estoque em uma página, considere as configurações que foram criadas usando a opção **Dimensões de exibição**. Por exemplo, se você usar a personalização para ocultar uma coluna para a dimensão do número do lote de estoque e a coluna for exibida na próxima vez que a página for aberta, isso pode ocorrer porque as configurações de exibição de dimensão controlam quais colunas de dimensões de estoque são exibidas. 

As configurações de exibição de dimensões se aplicam a todas as páginas e essas configurações substituirão qualquer configuração personalizada de campos de dimensão de estoque em páginas individuais. 

Para o exemplo com a dimensão do número do lote de estoque, a dimensão teria que ser desmarcada como parte da opção **Dimensões de exibição** para que a tabela não exibisse a coluna. Com o tempo, essa alteração seria aplicada não somente a uma página específica mas a todas as páginas.

