---
title: Visão geral de modelos e layouts
description: Este artigo aborda modelos e layouts no Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/26/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 0664dd1ae06d09557cf8b8ec58baf6d27c1198bd
ms.sourcegitcommit: 023ae5557e1351a8329a59a41a551e8901db99a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733375"
---
# <a name="templates-and-layouts-overview"></a>Visão geral de modelos e layouts


[!include [banner](includes/banner.md)]

Modelos são um elemento fundamental do modelo de página do Microsoft Dynamics 365 Commerce. Se seu objetivo é maximizar a eficiência e a consistência dos fluxos de trabalho de criação de sites, é importante que você aprenda como tirar proveito dos modelos para seu site. As decisões iniciais sobre a estrutura do modelo são importantes e podem afetar significativamente o custo e a agilidade das atualizações diárias, sazonais e de marca em todo o site. Modelos bem estruturados também têm outros benefícios. Por exemplo, eles ajudam a melhorar as pontuações de otimização de mecanismo de busca (SEO) em todo o site e a minimizar a contagem de bugs.

Uma boa maneira de começar a trabalhar com modelos é entender os benefícios funcionais dos modelos e layouts, as diferenças entre eles e a hierarquia.

A ilustração a seguir mostra a hierarquia do modelo de página atrás de uma página da Web renderizada.

![Diagrama do modelo de página.](../commerce/media/page-model-diagram.png)

| Entidade        | Função básica |
|---------------|----------------|
| Modelo      | Os modelos definem as opções do módulo e a estrutura básica de um conjunto de layouts e instâncias de página. |
| Layout        | Os layouts definem a seleção e a organização de final de módulos de uma página ou um conjunto de páginas. |
| Instância da página | As instâncias da página definem os dados e o conteúdo de páginas específico. |

## <a name="templates"></a>Modelos

Os modelos estão na parte superior da hierarquia do modelo de página do Dynamics 365 Commerce e representam uma importante etapa inicial da configuração do site. Os modelos ajudam a controlar a consistência em uma família de layouts e páginas filho, definindo a estrutura base e as opções de autoria para criação de layout downstream e fluxos de trabalho de criação de página. Os modelos podem ajudar a simplificar o processo de criação de conteúdo por meio de elementos predefinidos e gerenciados centralmente (como cabeçalhos e rodapés) e fluxos de criação guiados que ajudam a garantir que as opções de configuração do módulo sejam integradas à marca.

### <a name="controlling-consistency"></a>Consistência de controle

Ao criar um modelo, a maior decisão comercial que você deve tomar é quanto controle o modelo deve ter sobre o processo de criação da página. Um modelo que deixa tudo aberto para um autor de downstream é o tipo mais fácil de criar, mas pode ter consequências a longo prazo para a manutenção das páginas criadas a partir dele. Um modelo bem escrito fornece orientação e uma experiência de criação simplificada, mas também oferece aos autores flexibilidade suficiente para que eles possam concluir sua tarefa. Todos esses aspectos dependem do nível de controle que o modelo impõe.

Os modelos podem ajudar os autores de conteúdo a serem mais eficientes e permanecerem na marca das seguintes maneiras:

- Limitar os módulos que podem ser usados em uma página.
- Sugerir opções padrão de módulo e de configuração.
- Fazer explicitamente algumas opções de módulo e configuração que são controladas no nível do modelo. Esse processo é conhecido como uma configuração de *bloqueio* .

O exemplo a seguir mostra como um modelo básico (modelo X) pode ser configurado:

- Todos os layouts filhos do modelo X devem ter um contêiner de cabeçalho, um contêiner de corpo e um contêiner de rodapé.
- No modelo X, a configuração do contêiner de cabeçalho está bloqueada e pode ser alterada apenas no próprio modelo X. Todos os layouts e páginas filho sempre têm esse cabeçalho.
- O contêiner do corpo requer pelo menos um módulo e até um máximo de dez módulos. Esse módulos são definidos por layouts e páginas downstream.
- Para o contêiner do corpo, os módulos herói, recurso, carrossel e banner estão disponíveis.
- Um contêiner de rodapé é configurado no modelo X, mas pode ser substituído por layouts e páginas downstream.

O modelo neste exemplo define uma estrutura simples e um conjunto de opções para autores de conteúdo downstream. Observe que algumas partes de uma página (neste caso, o cabeçalho) estão totalmente definidas e bloqueadas no modelo e não podem ser alteradas pelos autores downstream. Outras partes (neste caso, o corpo) podem ser definidas por autores downstream dentro de diretrizes específicas (nesse caso, um número mínimo e um número máximo de módulos de tipos específicos). E outras partes (neste caso, o rodapé) são definidas no modelo, mas podem ser substituídas pelos autores a jusante.

Uma etapa inicial importante para os administradores de sites e de marca é determinar o equilíbrio correto entre restrição e flexibilidade para o layout filho e autores da página. Quando modelos são usados, esse saldo é completamente configurável. Isso afeta se os elementos da página são atualizados centralmente (bloqueados no modelo) ou deixados para níveis filho individuais que são mais baixos na hierarquia da página.

### <a name="relationship-between-template-defaults-and-page-content"></a>Relacionamento entre padrões de modelo e conteúdo de página

A função principal de um modelo é simplificar a experiência de criação de módulos quando uma página é criada. Mesmo quando os padrões de módulo são definidos ou até bloqueados em um modelo, não há nenhuma conexão de dados adicional das configurações de módulo de uma página para os padrões do modelo, exceto quando a página é editada. Os modelos controlam a experiência de criação da estrutura de página e depois que uma página é criada, os padrões do modelo não estão mais vinculados ao conteúdo localizável nessa página. Em outras palavras, os padrões do módulo que são definidos em um modelo controlam a experiência de criação de páginas filhas. Eles não controlam o conteúdo dessas páginas depois que as páginas são criadas e editadas.

A única exceção para o comportamento descrito anteriormente ocorre quando um [fragmento](work-with-fragments.md) é adicionado a um modelo. Os fragmentos podem ser usados para adicionar ou editar dinamicamente conteúdo localizável em todas as páginas filho de um modelo ou em um layout, a qualquer momento, mesmo depois que muitas páginas tiverem sido criadas a partir de um determinado modelo. A melhor prática é usar fragmentos em modelos e layouts sempre que conteúdo localizável tiver que ser adicionado, removido ou editado dinamicamente em todas as páginas filho. Por exemplo, os fragmentos devem ser usados para cabeçalhos, rodapés, metadados/scripts comuns ou qualquer outro conteúdo que deva ser editável centralmente e o mesmo em todas as páginas filho. Os fragmentos fornecem uma forma de usar modelos e layouts para controlar o conteúdo em todas as páginas filho.

Para começar a usar modelos, consulte [Trabalhar com modelos](work-with-templates.md).

## <a name="layouts"></a>Layouts

Layouts são o próximo nível na hierarquia do modelo de página, abaixo dos modelos. Enquanto um modelo define todos os módulos permitidos para uma página, um layout é uma seleção e organização explícitas de módulos. As páginas são o próximo nível na hierarquia do modelo de página, abaixo dos layouts. Eles definem o conteúdo localizado para os módulos selecionados no layout.

O exemplo a seguir baseia-se no exemplo de modelo da seção anterior e mostra como um layout básico pode ser configurado:

- O modelo pai do layout requer que o contêiner do corpo tenha entre um e dez módulos. Esses módulos podem ser apenas módulos herói, recurso, carrossel e banner. Portanto, o layout pode definir a seguinte seleção e organização dos módulos:

    - O primeiro módulo no contêiner do corpo é um módulo de banner e é seguido por um módulo de herói e dois módulos de recursos.
    - O primeiro módulo de recurso está alinhado à esquerda e o segundo módulo de recurso está alinhado à direita.

- Mesmo que um rodapé padrão seja herdado do modelo pai, o autor do modelo deixou o rodapé desbloqueado. Portanto, o layout pode substituí-lo definindo um fragmento de rodapé diferente.

O layout neste exemplo define a organização final dos módulos para páginas filhas. Como um modelo, um layout pode definir propriedades padrão ou bloqueadas do módulo que sempre serão herdadas pelas páginas filhas (por exemplo, o alinhamento dos módulos de recursos). O conteúdo ou os dados reais de cada módulo no layout são definidos mais abaixo na hierarquia, em cada instância da página filha. Uma distinção importante aqui é que os layouts não contêm diretamente conteúdo localizável, enquanto as páginas filhas deles contêm. A função principal do layout é definir a organização final e a configuração padrão dos módulos para suas páginas filhas.

A hierarquia é avançada por dois motivos. Primeiro, os layouts que compartilham o mesmo modelo pai são tratados como compatíveis com os cenários de troca de layout. Portanto, o layout de qualquer página pode ser alterado para outro layout da mesma hierarquia de modelos sem exigir que o conteúdo no nível da página seja re-criado. Você pode tirar proveito desse recurso para fazer atualizações sazonais do projeto, experimentar ou fazer uma reformulação permanente do site. Segundo, os layouts fornecem outra maneira de modificar centralmente os elementos compartilhados para um grupo de páginas sem exigir atualizações em páginas individuais. Por exemplo, se uma categoria de produto tiver 1.000 páginas que compartilham o mesmo layout, os módulos poderão ser reordenados no layout e essa alteração será refletida imediatamente em todas as 1.000 páginas filhas.

Ao entender essa hierarquia, você pode fornecer uma estrutura de site ágil e eficiente que ajuda a economizar custos, é escalável e produz melhores resultados, conforme o site evolui com o tempo.

### <a name="preset-and-custom-layouts"></a>Layouts predefinidos e personalizados

Os layouts de seu site podem ser *predefinidos* ou *personalizados*:

- Os **Layouts predefinidos** permitem um fluxo de trabalho de criação de página em que todos os módulos já estejam selecionados e organizados e somente a entrada de dados seja necessária. Essa abordagem pode ajudar a economizar tempo quando muitas páginas devem ser criadas com os mesmos requisitos de layout. Os layouts predefinidos têm um relacionamento de um para muitos com as páginas filho. Portanto, um único layout predefinido pode ser usado para controlar centralmente a organização do módulo para centenas ou milhares de páginas filhas.
- **Layouts personalizados** são essencialmente layouts de uso único incorporados em uma página. Eles não são expostos como uma opção quando outras novas páginas são criadas ou em cenários de troca de layout. O benefício dessa abordagem é que um autor pode experimentar criando uma página que usa um layout personalizado. Então, se o autor quiser reutilizar o layout para outras páginas, ele poderá ser facilmente convertido em um layout predefinido. O novo layout predefinido é exposto como uma opção nos fluxos de trabalho de criação de página e nos cenários de troca de layout para páginas da mesma hierarquia de modelos. Por outro lado, layouts predefinidos podem ser ramificados em layouts personalizados. Dessa forma, um autor pode separar uma página do layout predefinido e criar um novo layout personalizado de uso único. (Esse novo layout personalizado ainda está vinculado por quaisquer restrições no modelo pai).

O layout predefinido e os layouts personalizados são editados em diferentes partes do conjunto de ferramentas de criação. Como os layouts personalizados não dependem de outras páginas, eles são editados diretamente no editor de páginas. Nesse caso, a existência de um layout é transparente para o usuário e é exposta apenas nas propriedades no nível da página e através das ações para opções de layout. No entanto, como as alterações nos layouts predefinidos podem afetar muitas páginas filhas, elas devem ser editadas no editor de layout, onde as ações de publicação consideram o impacto total do downstream nas páginas filhas.

A ilustração a seguir mostra cenários de layouts predefinidos e personalizados.

![Cenários de layout predefinidos e personalizados.](../commerce/media/template-figure1.png)

Para começar a usar layouts predefinidos, consulte [Trabalhar com layouts predefinidos](work-with-layouts.md).

## <a name="additional-resources"></a>Recursos adicionais

[Trabalhar com modelos](work-with-templates.md)

[Trabalhar com layouts predefinidos](work-with-layouts.md)

[Trabalhar com grupos de publicações](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
