---
title: "Personalizar a experiência do usuário"
description: "Este artigo explica como é possível personalizar o Microsoft Dynamics 365 for Operations."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserSetup
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 8965c193839002776b3c61036b23b54625c974a4
ms.lasthandoff: 03/31/2017


---

# <a name="personalize-the-user-experience"></a>Personalizar a experiência do usuário

[!include[banner](../includes/banner.md)]


Este artigo explica como é possível personalizar o Microsoft Dynamics 365 for Operations.

Há vários tipos de personalizações no Microsoft Dynamics 365 for Operations. Algumas personalizações são as seleções feitas em uma lista de opções em uma página de configuração. Algumas personalizações são implícitas; por exemplo, o Microsoft Dynamics 365 for Operations controla as larguras das colunas de grade se você ajustá-las e o estado expandido/recolhido das Guias Rápidas. Outras personalizações são explícitas. Para personalizações explícitas, você entra em um modo de personalização interativo e modifica a aparência de uma página ao gerenciar diretamente a forma como esses elementos aparecerão ou atuarão na página. 

Qualquer tipo de personalização feita por um usuário no Microsoft Dynamics 365 for Operations destina-se somente a esse usuário, independentemente da empresa com a qual o usuário interage. As alterações que um usuário faz em uma página não afetam outros usuários no sistema.

## <a name="systemwide-options-for-the-current-user"></a>Opções no nível do sistema para o usuário atual
Na barra de navegação, você encontrará a imagem de uma engrenagem, que é o botão de menu **Configurações**. Ao abrir o menu **Configurações**, você verá uma série de opções. Selecionar **Opções** abrirá a página **Opções** do usuário. Você verá quatro guias de opções: **Visual**, **Preferências**, **Conta** e **Fluxo de trabalho**.

-   **Visual: **use-a para escolher um tema de cor e o tamanho padrão dos elementos nas páginas.
-   **Preferências:** Aqui você pode escolher padrões cada vez que abrir o Microsoft Dynamics 365 for Operations, incluindo a empresa, a página inicial e o modo exibição/edição padrão (que determina se uma página será bloqueada para exibição ou aberta para edição cada vez que for aberta). Você também encontrará opções de idioma, fuso horário, data, hora e formato de número. Por fim, esta página contém preferências diversas que variarão de acordo com a versão.
-   **Conta: **fornece a ID do usuário e outras opções relacionadas à conta.
-   **Fluxo de trabalho: **aqui é possível escolher opções relacionadas ao fluxo de trabalho.

## <a name="implicit-personalizations"></a>Personalizações implícitas
As personalizações implícitas são aquelas que você executa ao interagir com alguns controles que reconhecem seu estado de visibilidade atual. 

**Colunas de grade:** você pode ajustar a largura de uma coluna em uma lista ao selecionar a barra de dimensionamento à esquerda ou à direita do cabeçalho da coluna e deslizá-la para esquerda ou direita até a largura desejada. O Microsoft Dynamics 365 for Operations armazenará a largura de sua preferência e exibirá essa coluna com essa largura todas as vezes que você abrir a página com essa lista. 

**Guias Rápidas:** algumas páginas têm seções expansíveis chamadas Guias Rápidas. O Microsoft Dynamics 365 for Operations armazenará as Guias Rápidas que você expandiu e as Guias Rápidas que você recolheu. Cada vez que você retornar à página, as mesmas Guias Rápidas estarão expandidas ou recolhidas, com base na sua última utilização. Neste artigo, explicaremos como alterar a ordem das seções das Guias Rápidas. Em alguns casos, recolher uma Guia Rápida pode melhorar o desempenho, pois o Microsoft Dynamics 365 for Operations não precisará recuperar as informações dessa Guia Rápida até que ela seja expandida. 

**Quadro de Fatos:** algumas páginas têm uma seção Quadro de Fatos. Esse painel contém informações somente leitura relacionadas ao assunto atual da página. Cada seção no painel Quadro de Fatos é chamada de Quadro de Fatos. Você pode expandir ou recolher um Quadro de Fatos e o Microsoft Dynamics 365 for Operations armazenará sua preferência. Em alguns casos, recolher um Quadro de Fatos pode melhorar o desempenho, pois o Microsoft Dynamics 365 for Operations não precisará recuperar as informações desse Quadro de Fatos até que ele seja expandido.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Personalizações explícitas usando a barra de ferramentas Personalização
Cada pessoa e empresa têm uma perspectiva diferente de quais dados são mais importantes ou quais dados não são necessários para a maneira como eles conduzem seus negócios. A capacidade de personalizar a maneira como você organiza as informações, interage ou até mesmo oculta suas informações é a chave para tornar o Microsoft Dynamics 365 for Operations uma experiência pessoal e produtiva. 

As personalizações explícitas são aquelas executadas explicitamente com a intenção de alterar a aparência ou comportamento de um elemento ou de uma página, escolhendo a partir de um menu de personalização. O tipo mais básico de personalização explícita é quando você clica co o botão direito em um elemento e seleciona **Personalizar**. (Observe que nem todos os elementos na página podem ser personalizados.) Quando você seleciona esse método de personalização, verá a janela de propriedades do elemento. 

[![Personalizando propriedades de um elemento](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg) 

Você personalizará um elemento na página dessa maneira se quiser apenas alterar o rótulo do elemento, ocultar o elemento para que ele não seja exibido na página (isso não altera nenhum dado, isso simplesmente não exibe a informação), incluir as informações na seção de resumo da Guia Rápida (se o elemento estiver em uma Guia Rápida), ignorar o campo ao usar a tabulação ou fazer isso para que os dados não possam ser alterados por meio da marcação “Não Editar.” 

Para mover ou ocultar elementos ou fazer várias alterações, use a barra de ferramentas Personalização, disponível na janela de Propriedade dos elementos quando você escolhe **Personalize este formulário**. A barra de ferramentas Personalização também está disponível no Painel de ação do formulário, no grupo Personalizar da guia **Opções**. Selecione **Personalize este formulário**, e você verá a barra de ferramentas Personalização. 

[![Barra de ferramentas de personalização](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

A barra de ferramentas Personalização tem uma série de ações de personalização. Escolha a ferramenta **Selecionar** para selecionar e alterar as propriedades de vários elementos, um de cada vez. Primeiro, clique na ferramenta Selecionar e, depois, clique no elemento cujas propriedades você deseja modificar. Quando você selecionar um elemento, a janela de propriedades do elemento será aberta e você poderá modificar qualquer propriedade desse elemento. Você pode repetir o processo para outros elementos personalizáveis no formulário. Em alguns casos, você selecionará um elemento e perceberá que algumas propriedades não são modificáveis. Isso significa que, com base na forma como o elemento atual é usado, o Microsoft Dynamics 365 for Operations não permite alterar essa propriedade. Por exemplo, você não pode ocultar um campo obrigatório. 

Escolha a ferramenta **Mover** quando quiser selecionar e mover um elemento para um local diferente no grupo atual de elementos. (Você não pode mover um elemento para fora de seu grupo pai). Primeiro, clique na ferramenta Mover e, em seguida, clique no elemento que deseja mover. Quando você clica no elemento a ser movido, o Microsoft Dynamics 365 for Operations verifica o formulário para saber para onde esse elemento pode ser movido e cria uma série de "zonas para soltar". Essas zonas são exibidas como uma linha colorida em negrito, ao lado da área em que o elemento pode ser solto, enquanto você arrasta o elemento para o grupo atual. 

Escolha a ferramenta **Ocultar** para selecionar e ocultar um elemento. Para ocultar um elemento, basta escolher a ferramenta Ocultar e clicar no elemento que você deseja ocultar. Quando você escolher a ferramenta Ocultar, todos os elementos ocultos atuais ficarão visíveis e serão exibidos em um contêiner sombreado, para que você possa escolher o elemento que será reexibido. Escolha a ferramenta Selecionar para ver a aparência da página com os elementos ocultos selecionados. Escolha a ferramenta **Resumo** quando quiser que um campo numérico ou de cadeia de caracteres seja exibido na área de resumo da Guia Rápida. A ferramenta Resumo se aplicará somente a campos que estejam contidos em uma seção de Guia Rápida. Quando você escolhe a ferramenta Resumo, o Microsoft Dynamics 365 for Operations exibe todos os campos que foram selecionados como campos de resumo, colocando-os em um contêiner sombreado. Você pode adicionar e remover interativamente campos de um resumo da Guia Rápida clicando no campo. 

Escolha a ferramenta **Ignorar** para remover um elemento da sequência de guias de teclado da página. Quando você escolher a ferramenta Ignorar, todos os elementos atualmente ignorados serão exibidos em um contêiner sombreado, para que você possa escolhê-los novamente e torná-los parte da sequência de guias. 

Escolha a ferramenta **Editar** para marcar um elemento como Editável ou Não Editável. Quando você escolhe a ferramenta Editar, todos os elementos não editáveis atuais são exibidos em um contêiner sombreado, para que você possa escolhê-los para torná-los editáveis. Observe que alguns campos são obrigatórios e não podem se tornar não editáveis. Esses campos aparecerão com um ícone de cadeado. 

Escolha a ferramenta **Adicionar** para adicionar um campo à página. Com a ferramenta Adicionar, não é possível criar um campo novo, mas você pode adicionar campos que já fazem parte da definição de página atual e não estão exibidos na página. Ao escolher a ferramenta Adicionar, você precisará primeiro selecionar o grupo ou a área ao qual deseja adicionar um campo. Uma caixa de diálogo exibirá a lista de campos relacionados à seção que você selecionou. Nessa caixa de diálogo, você pode selecionar um ou mais campos a serem adicionados e clicar em Inserir. Se, posteriormente, você desejar remover um campo já adicionado, repita o processo, mas apenas limpe o campo que adicionou. 

Escolha o botão **Gerenciar** para ver uma lista de opções de gerenciamento relacionada a todas personalizações da página atual. 

Escolha **Limpar** para redefinir a página a seu padrão, estado instalado. Todas as personalizações na página atual serão limpas. Não há ação para desfazer, então use apenas essa opção quanto estiver certo que deseja redefinir sua página. 

Escolha **Importar** para usar a personalização de um arquivo de personalização que você ou outra pessoa criaram previamente para essa página. Importar uma personalização removerá todas as personalizações existentes na página e usará todas as personalizações do arquivo selecionado. Se você quiser salvar ou compartilhar uma personalização, selecione a opção **Exportar** para salvar as personalizações em um arquivo. 

Escolha o botão **Fechar** para fechar a barra de ferramentas e retornar a página ao seu estado interativo anterior. 

Com a barra de ferramentas Personalização, o salvamento é implícito. As personalizações são efetuadas imediatamente; não é necessário clicar no botão **Salvar**. Em alguns casos, você verá um ícone de cadeado próximo a um elemento quando selecionar uma ferramenta. Isso significa que, para que a página funcione corretamente, você não pode modificar as propriedades relacionadas à ferramenta selecionada. Quando a barra de ferramentas Personalização for aberta, a página se tornará não interativa. Você não pode inserir dados nem expandir ou recolher seções.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Personalização explícita: Adicionando um bloco ou uma lista a um espaço de trabalho
Algumas páginas com listas terão um recurso adicional de personalização disponível no Painel de Ação, no grupo Personalizar da guia Opções. Selecione **Adicionar ao Espaço de Trabalho** para abrir a lista suspensa que permite exibir as informações da lista atual (filtrada e classificada ou padrão) em um Espaço de Trabalho como uma lista ou bloco resumido (que pode ser usado para exibir o número de itens na lista). 

[![Adicionar ao espaço de trabalho](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Para adicionar uma lista a um espaço de trabalho, primeiro classifique ou filtre a lista do modo como você gostaria de vê-la em seu espaço de trabalho e, em seguida, selecione a caixa de diálogo Adicionar ao Espaço de Trabalho. Em seguida, selecione o espaço de trabalho desejado e selecione **Lista** na lista suspensa Apresentação. Quando você selecionar **Lista**, uma caixa de diálogo será aberta, permitindo que você escolha as colunas que deseja ver na lista, e a rótulo da lista conforme aparece no espaço de trabalho. 

Para adicionar um bloco a um espaço de trabalho, primeiro filtre a lista para representar os dados que você deseja resumir (ou deseja acessar rapidamente). Em seguida, abra a caixa de diálogo suspensa Adicionar ao Espaço de Trabalho. Depois, selecione o espaço de trabalho desejado e selecione **Bloco** na lista suspensa Apresentação. Quando você selecionar **Bloco**, uma caixa de diálogo será aberta, permitindo que você forneça um rótulo de bloco e decida se o bloco exibirá uma contagem. Quando inserido em um espaço de trabalho, o bloco permitirá que você abra a página atual do espaço de trabalho e exiba a lista de informações relacionadas ao bloco. 

Quando a lista ou o bloco é adicionado a um espaço de trabalho, você poderá abrir esse espaço de trabalho e reordenar a lista ou o bloco no grupo em que ele foi inserido.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Personalização explícita: Adicionando um resumo de um espaço de trabalho a um painel
Alguns espaços de trabalho contém os blocos de contagem (blocos com números neles) que você também gostaria de ver no painel. Em um espaço de trabalho, clique com o botão direito em um bloco de contagem e selecione **Personalizar**. Selecione **Fixar no Painel**. Na próxima vez que você navegar para (e atualizar) o painel selecionado, verá essa contagem abaixo do bloco de navegação do espaço de trabalho no painel.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Personalização explícita: Personalizando o painel
Geralmente, o painel é a primeira página que você vê quando abre o Microsoft Dynamics 365 for Operations. Você pode personalizar o painel para renomear os blocos de navegação do espaço de trabalho, exibir somente os blocos desejados, renomear os blocos ou organizar os blocos na ordem em que você preferir consultá-los. Para personalizar o painel, selecione qualquer bloco e clique com o botão direito do mouse para abrir um menu de contexto. No menu de contexto, selecione **Personalizar**. Se o bloco selecionado for o que você deseja ocultar, renomear ou ignorar, faça essa alteração diretamente na janela Propriedade exibida. Para organizar os blocos, selecione **Personalizar este formulário** na janela Propriedade para abrir a barra de ferramentas Personalização. Você pode usar a ferramenta Mover para organizar os blocos.

## <a name="administration-of-personalization"></a>Administração de personalização
É possível personalizar uma página e compartilhá-la com outros usuários; para isso, basta exportar a página personalizada e solicitar a outros usuários que naveguem até a página personalizada e importem o arquivo de personalização que você criou. Se um usuário tiver privilégios de administrador, ele também poderá gerenciar personalizações para outros usuários na página **Configuração da Personalização**. Navegue até a página b. Na página **Personalização**, você encontrará duas guias: **Sistema** e ** Usuários**. 

**Sistema:** aqui é possível desabilitar ou "desativar" temporariamente todas as personalizações do sistema. Isso não exclui as personalizações, apenas redefine todos os formulários para seu estado padrão. Mais tarde, você poderá habilitar novamente a personalização para que todas as personalizações sejam reaplicadas aos formulários de cada usuário. Também é possível excluir todas as personalizações de todos os usuários. Observe que, quando você exclui as personalizações, não há como reabilitar automaticamente as personalizações do sistema. Antes de executar essa etapa, verifique se você exportou as personalizações que talvez deseje importar posteriormente. 

**Usuários:** aqui você pode decidir para cada usuário se eles podem realizar uma personalização implícita ou explícita. Você também pode decidir se cada usuário pode realizar a personalização implícita ou explícita em um formulário específico. Por fim, você pode importar, exportar ou excluir uma personalização de cada usuário. 

**Observação:** em seu lançamento inicial, a administração de personalização permite apenas o gerenciamento por usuário.



