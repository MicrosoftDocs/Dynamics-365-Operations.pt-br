---
title: Versões de engenharia e categorias de produtos de engenharia
description: Este tópico fornece informações sobre o conceito de versões de engenharia. As versões de engenharia garantem que os diferentes estados de um produto e seus dados sejam mantidos atuais e claros, e que possam ser visualizados no sistema.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgLookupDynastring, EngChgProductVersionNumberRule, EngChgEcmProductRoute, EngChgEcmRequestProducts, EngChgEcmProductRoute, EngChgEcmProductPreview,EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmProductCreate, EngChgEcmProductLookup, EngChgProductVersionPrCompany, ngChgProductTypeLookup, EngChgProductType, EngChgProductItemPart, EngChgProductItem, EngChgEcmCategory, EngChgEcmBomDesignerEditBom, EngChgEcmBomDesigner, EngChgEcmBOMCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 3eb5b5c4304b393008ecc5f5ff5a663295ed0d22
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4422630"
---
# <a name="engineering-versions-and-engineering-product-categories"></a>Versões de engenharia e categorias de produtos de engenharia

[!include [banner](../includes/banner.md)]

Os produtos de engenharia evoluem durante o ciclo de vida do produto, por vários motivos. Por exemplo, as alterações podem ser apresentadas para melhorar a manutenção do produto, alterar um componente porque o fornecedor não o oferece mais, responder a novas ideias ou corrigir erros no design inicial. Também há várias razões pelas quais essas alterações devem ser armazenadas como parte de um produto em andamento, de tal forma que os dados anteriores não sejam substituídos. Estes são alguns motivos:

- Você deseja manter o controle do produto pois ele foi fabricado e entregue a clientes em estados de ciclo de vida anteriores.
- Você precisa de um prazo de entrega antes de aprovar e aplicar as alterações.
- Você deseja ter um carimbo de data/hora em cada alteração e ser capaz de entregar produtos fabricados anteriormente separados uns dos outros.

As *versões de engenharia* garantem que os vários estados de um produto e seus dados sejam mantidos atuais e claros, e que possam ser visualizados no sistema. Esse conceito ajuda a manter a consistência, bloquear a BOM (lista de materiais) para produção, eliminar variabilidade e facilmente identificar alterações.

Geralmente, a regra *forma-adequação-função* é aplicada para determinar se uma alteração exige um novo produto, uma nova versão ou uma atualização de uma versão existente. Cada um dos três termos no nome desta regra se refere a um aspecto específico de uma peça, o que ajuda os engenheiros a correlacionar peças às necessidades. A regra forma-adequação-função aumenta a flexibilidade das alterações de design, pois a documentação mínima e o custo de design são necessários para alterar uma peça, desde que a adequação, a forma e a função do produto sejam mantidas.

- **Adequação** se refere à capacidade da peça ou do recurso de se conectar, se acoplar ou se unir a outro recurso ou peça em uma montagem. A adequação permite que a peça cumpra as tolerâncias de montagem exigidas para que possa ser útil.
- **Forma** refere-se a características de uma peça ou montagem, como dimensões externas, peso, tamanho e aparência visual. A forma é o aspecto mais afetado pelas opções estéticas de um engenheiro. Ela inclui o compartimento, o chassi e o painel de controle, que se tornam a "face" externa do produto.
- **Função** é um critério que é atendido quando a peça cumpre sua finalidade de forma eficiente e confiável. Por exemplo, em um produto eletrônico, a função pode depender dos componentes de estado sólido usados e do software ou firmware. Geralmente, ela também pode depender dos recursos do compartimento selecionado. Dois dos motivos mais comuns pelos quais um compartimento pode falhar no critério de função são portas mal colocadas ou de tamanho incorreto, e etiquetas enganosas ou ausentes. 

## <a name="engineering-versions"></a>Versões de engenharia

Ao usar produtos de engenharia, cada produto tem pelo menos uma versão de engenharia. A versão inicial da engenharia é criada automaticamente quando você cria um produto de engenharia. Cada versão de engenharia armazena os dados relevantes da engenharia que são específicos dessa versão. Veja alguns exemplos desses dados:

- O número da versão e o número da versão anterior (se aplicável)
- As datas de efetivação inicial e final
- O status ativo da versão do produto, que indica se a versão pode ser liberada e usada em transações (Para obter mais informações, consulte [Preparo do produto](product-readiness.md).)
- A empresa de engenharia que criou e possui o produto (Para obter mais informações sobre empresas de engenharia e empresas operacionais, consulte [Empresas de engenharia e regras de propriedade de dados](engineering-org-data-ownership-rules.md).)
- Documentos de engenharia relacionados, como um manual de montagem, instruções do usuário, imagens e links
- Os atributos de engenharia (Para obter mais informações, consulte [Atributos de engenharia e pesquisa de atributos de engenharia](engineering-attributes-and-search.md).)
- As BOMs de engenharia
- Os roteiros de engenharia

Você pode atualizar esses dados em uma versão existente ou criar uma nova versão, usando uma *ordem de alteração de engenharia*. (Para obter mais informações, consulte [Gerencie alterações em produtos de engenharia](engineering-change-management.md).) Se você criar uma nova versão de um produto, o sistema copiará todos os dados relevantes da engenharia para essa nova versão. Você pode modificar os dados dessa nova versão. Dessa forma, você pode rastrear dados específicos de cada versão consecutiva. Para comparar as diferenças entre versões de engenharia consecutivas, inspecione a ordem de alteração da engenharia, que inclui tipos de alteração que indicam todas as alterações.

Como foi indicado, a versão inicial da engenharia é criada automaticamente quando você cria um produto de engenharia. O número de versão dessa versão segue a regra de número de versão definida na categoria de engenharia do produto. Para fazer a transição para uma versão subsequente, você deve adicionar o produto a uma ordem de alteração de engenharia como uma linha e deve definir o campo **Impacto** como *Nova versão*. A ordem de alteração de engenharia incluirá os detalhes da alteração da versão atual para a próxima versão.

Observe que um produto de engenharia só pode estar em uma ordem de alteração de engenharia por vez. Essa restrição garante a precisão dos dados e ajuda a evitar alterações sobrepostas ou contraditórias no produto. Note também que o campo **Engenheiro** na exibição **Cabeçalho** da ordem de alteração de engenharia mostra o engenheiro responsável pela ordem de alteração. Se o engenheiro pertencer a uma equipe definida no sistema, o campo **Responsável** mostrará o líder dessa equipe.

## <a name="track-versions-in-transactions"></a>Rastrear versões em transações

Quando você usa o gerenciamento de alterações de engenharia, os dados mestre do produto sempre incluem uma ou mais versões de engenharia. Na configuração de produtos de engenharia, você pode escolher se a versão de engenharia também faz parte das *transações logísticas*. (Para obter mais informações, consulte a seção [Configurar categorias de produtos de engenharia](#product-category) mais adiante neste tópico.) Se o impacto logístico for relevante, ele será diferente por produto e por empresa. Às vezes, somente a versão mais recente de um produto é usada. Portanto, quando você apresentar uma nova versão, a versão anterior não poderá mais ser usada. Em outros casos, a versão anterior é necessária em transações logísticas para superar os seguintes desafios:

- O departamento de logística deve enviar duas peças de um produto para um cliente. Nesse caso, você deve decidir se deseja ou permite que duas versões diferentes sejam enviadas.
- Depois, será descoberto que ocorreu um problema e que ele está relacionado a uma alteração específica. Nesse caso, talvez seja benéfico determinar exatamente qual versão foi enviada em cada ordem.
- As empresas, em geral, desejam enviar versões antigas primeiro para retirá-las do estoque. Especialmente para produtos de baixo volume, essa abordagem pode ser gerenciada com frequência, determinando as datas de efetividade da nova versão em relação a previsões sobre quando o estoque da versão antiga será esgotado. No entanto, às vezes talvez você não consiga fazer essa comparação ou possa considerar as incertezas de previsões em nível de estoque muito altas.

A decisão de tornar as versões visíveis no estoque depende de fatores como os citados previamente, além da prática da empresa e de outras considerações específicas de cada empresa. Você pode especificar o comportamento da *categoria de produtos de engenharia*. Ele será aplicado a todos os produtos criados a partir dessa categoria para todas as empresas para as quais o produto for liberado.

Para produtos configurados de forma que tenham impacto logístico, a versão de engenharia deve ser especificada em cada transação. Embora o sistema proponha a *versão mais recente ativa*, você pode selecionar entre todas as versões ativas disponíveis para a empresa. Para produtos configurados de forma que não tenham impacto logístico, a versão de engenharia não é especificada em transações. No entanto, o sistema usa a versão mais recente ativa. Por exemplo, quando você adicionar um produto a uma BOM de produção, a última versão será usada e, quando executar o planejamento mestre, a versão mais recente será presumida.

## <a name="set-up-engineering-product-categories"></a><a name="product-category"></a>Configurar categorias de produto de engenharia

Uma categoria de produto de engenharia oferece uma base para criar um produto de engenharia específico. Cada categoria estabelece um conjunto de valores e políticas padrão. Portanto, ao criar um produto de engenharia, primeiro selecione a categoria da qual ele será criado.

Observe que um novo tipo de hierarquia de categorias (*hierarquia de produtos de engenharia*) é configurado automaticamente para você. Você pode criar manualmente as categorias acessando **Gerenciamento de alterações de engenharia \> Configuração \> Detalhes da categoria de produtos de engenharia**.

Cada categoria de produto de engenharia estabelece o comportamento padrão dos produtos de engenharia criados com base nessa categoria. Depois de criar um produto de engenharia, não é possível alterar a categoria de produto de engenharia. No entanto, se você selecionar a categoria incorreta, poderá excluir o produto e recriá-lo.

Quando uma categoria de produto de engenharia é criada, você impede que as seguintes configurações sejam alteradas:

- Empresa de engenharia
- Tipo de Produto
- Subtipo do produto
- Grupo de dimensões do produto
- Tecnologia de configuração
- Regra de número de versão

Outras configurações podem herdar valores padrão que são configurados para a categoria de produto de engenharia. No entanto, de acordo com as regras do sistema, esses valores podem ser alterados.

Para trabalhar com categorias de produtos de engenharia, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Detalhes da categoria de produto de engenharia**. Siga uma destas etapas.

- Para criar uma nova categoria, selecione **Novo** no Painel de Ações e defina os campos conforme descrito nas subseções a seguir.
- Para editar uma categoria existente, selecione-a no painel de lista, selecione **Editar** no Painel de Ações e defina os campos conforme descrito nas subseções a seguir.
- Para excluir uma categoria existente, selecione-a no painel de lista e, depois, selecione **Excluir** no Painel de Ações.

### <a name="header"></a>Cabeçalho

Defina os campos a seguir no cabeçalho de uma categoria de produto de engenharia.

| Campo | descrição |
|---|---|
| Organização | Insira um nome para a categoria de produto de engenharia. |
| Empresa de engenharia | Selecione a empresa de engenharia em que os produtos dessa categoria de produto de engenharia podem ser criados e onde serão mantidos. |

### <a name="details-fasttab"></a>FastTab Detalhes

Defina os campos a seguir na FastTab **Detalhes** de uma categoria de produto de engenharia.

| Campo | descrição |
|---|---|
| Tipo de Produto | Selecione se a categoria se aplica a produtos ou serviços. |
| Rastrear versões em transações | Selecione se a versão do produto deve ser carimbada em todas as transações (impacto logístico). Por exemplo, se você rastrear a versão em transações, cada ordem de venda mostrará qual versão específica do produto foi vendida nessa ordem de venda. Se você não rastrear a versão em transações, as ordens de venda não mostrarão qual versão específica foi vendida. Em vez disso, elas sempre mostram a versão mais recente.<ul><li>Se esta opção estiver definida como *Sim*, um produto mestre será criado para o produto e cada versão do produto será uma variante que usa a dimensão de produto da *versão*. O campo **Subtipo de produto** é automaticamente definido como *Produto mestre* e você deve selecionar um grupo de dimensões de produto no qual a dimensão de *versão* está ativa. Somente os grupos de dimensões do produto em que a *versão* for uma dimensão ativa serão mostrados. Você pode criar novos grupos de dimensões do produto, selecionando o botão **Editar** (símbolo de lápis).</li><li>Se esta opção estiver definida como *Não*, a dimensão do produto da *versão* não será usada. Você poderá selecionar se deseja criar um produto ou um produto mestre que use as outras dimensões.</li></ul><p>Esta opção geralmente é usada para produtos que têm uma diferença de custo entre versões ou produtos em que diferentes condições se aplicam ao cliente. Portanto, é importante indicar a versão que foi usada em cada transação.</p> |
| Subtipo do produto | Selecione se a categoria conterá produtos ou produtos mestres. No caso de produtos mestres, serão usadas as dimensões do produto.
| Grupo de dimensões do produto | A configuração **Rastrear versões em transações** ajuda a selecionar o subtipo de produto. Se você tiver especificado que deseja rastrear a versão em transações, serão mostrados os grupos de dimensões do produto em que a dimensão *versão* será usada. Caso contrário, só serão mostrados grupos de dimensões do produto em que a dimensão *versão* não é usada. |
| Estado do ciclo de vida do produto | Configure o estado de ciclo de vida do produto padrão que um produto de engenharia deve ter ao ser criado pela primeira vez. Para obter mais informações, consulte [Estados e transações de ciclo de vida do produto](product-lifecycle-state-transactions.md). |
| Regra de número de versão | Selecione a regra do número de versão que se aplica à categoria:<ul><li>**Manual** – você escolhe o número da versão para cada nova versão.</li><li>**Automático** – o sistema define o número da versão com base em um formato definido por você. Ao configurar o formato, use um sinal numérico (\#) para representar um dígito e qualquer outro caractere para representar um valor constante. Por exemplo, se você definir o formato como *V-\#\#*, a primeira versão será "V-01", a segunda versão será "V-02" e assim por diante.</li><li>**Lista** – o sistema recebe o próximo número de uma lista predefinida de valores personalizados definidos por você.</li></ul> |
| Impor efetividade | Selecione se as datas de efetividade das versões de engenharia devem ser contíguas ou se podem existir lacunas e sobreposições. Esta configuração afeta a forma como você pode usar os campos **Efetivo a partir de** e **Efetivo até** para cada versão de engenharia em que a categoria se aplica.<ul><li>Se esta opção for definida como *Sim*, um valor **Efetivo a partir de** deverá ser especificado a cada versão; sobreposições e lacunas não serão permitidas entre versões. O intervalo de datas para cada versão de engenharia é conectado diretamente às versões anteriores e posteriores da engenharia, caso existam. Neste cenário, a versão mais recente é sempre usada e as versões mais antigas não são mais usadas.</li><li>Se esta opção estiver definida como **Não**, não haverá restrições nos campos de data de efetividade para versões de engenharia; sobreposições e lacunas são permitidas. Neste cenário, várias versões podem estar ativas ao mesmo tempo e você pode trabalhar com qualquer versão ativa.</li></ul><p>Esta opção também afeta BOMs e roteiros que estão conectados a uma versão do produto. Para obter mais informações, consulte a seção [Conectar BOMs e roteiros a versões de engenharia](#boms-routes) mais adiante neste tópico.</p> |
| Usar nomenclatura da regra de número | Defina esta opção como *Sim* para habilitar regras para definir um número de produto usando sequências numéricas, nomes e valores de atributos de engenharia e constantes de texto como segmentos. Para criar ou modificar regras, selecione o botão **Editar**. |
| Usar nomenclatura da regra de nome | Defina esta opção como *Sim* para habilitar regras para definir um nome usando os nomes de atributos de engenharia, valores de atributos de engenharia e constantes de texto como segmentos. Para criar ou modificar regras, selecione o botão **Editar**. |
| Usar nomenclatura da regra de descrição | Defina esta opção como *Sim* para habilitar regras para definir a descrição usando os nomes de atributos de engenharia, valores de atributos de engenharia e constantes de texto como segmentos. Para criar ou modificar regras, selecione o botão **Editar**. |

### <a name="attributes-fasttab"></a>FastTab Atributos

Use a grade na FastTab **Atributos** para configurar os atributos de engenharia que se aplicam a produtos que pertencem a essa categoria. Para obter informações sobre como criar atributos de engenharia, consulte [Atributos de engenharia e pesquisa de atributos de engenharia](engineering-attributes-and-search.md).

Use os botões da FastTab **Atributos** para adicionar, remover e organizar atributos na grade.

Se você alterar a seleção de atributos para uma categoria de engenharia e já existirem produtos baseados nessa categoria, você deverá decidir se deseja aplicar suas alterações a esses produtos. Se você desejar que os produtos existentes reflitam as alterações, selecione **Atualizar produtos existentes** na FastTab **Atributos**.

Para cada linha adicionada à grade, defina os campos a seguir.

| Campo | descrição |
|---|---|
| Organização | Selecione o atributo a ser adicionado. |
| Alíquota | Selecione o valor padrão para o atributo. |
| Obrigatório | Para atributos do tipo *booliano*, se esta opção estiver definida como *Sim*, os usuários deverão definir o atributo como *Sim*. Se esta opção estiver definida como *Não*, os usuários poderão definir o atributo como *Sim* ou *Não*. Para outros tipos de dados, a configuração dessa opção é apenas informativa. |
| Atributo de lote | Selecione se o atributo deve ser propagado por meio da funcionalidade em lotes. |

### <a name="readiness-policy-fasttab"></a>FastTab de política de preparo

Use o campo **Política de preparo de produtos** para selecionar a política de preparo que se aplica a produtos que pertencem a essa categoria. Para obter mais informações, consulte [Preparo do produto](product-readiness.md).

### <a name="release-policy-fasttab"></a>FastTab Política de liberação

Use o campo **Política de liberação de produtos** para selecionar a política de liberação que se aplica a produtos que pertencem a essa categoria. Para obter mais informações, consulte [Liberar estruturas de produtos](release-product-structure.md).

## <a name="connect-boms-and-routes-to-engineering-versions"></a><a name="boms-routes"></a>Conectar BOMs e roteiros a versões de engenharia

A configuração da opção **Aplicar efetividade** é importante para a conexão de BOMs e roteiros para cada versão de engenharia. Você poderá ativar várias BOMs ou roteiros por produto somente se houver uma diferença em uma das seguintes configurações:

- Dimensão do produto
- Quantidade
- Site
- Datas de efetividade

As BOMs e os roteiros de engenharia são criados a partir da versão de engenharia em que se aplicam. Eles podem ser reconhecidos pela marca de seleção na caixa de seleção **Engenharia controlada**. Ao trabalhar com roteiros e BOMs de engenharia, você em geral não os cria usando quantidades diferentes. Normalmente, você também não criará BOMs diferentes por site. Além disso, para roteiros e BOMs de engenharia, as datas de efetividade sempre são obtidas a partir da versão de engenharia. Portanto, uma versão de engenharia, sua BOM e seu roteiro terão as mesmas datas de efetividade.

Para produtos em que você está usando a dimensão de produto da *versão* (junto com impacto logístico nas transações), a versão também é adicionada às BOMs e roteiros. Esse comportamento ajuda a diferenciar as BOMs e os roteiros de versões consecutivas, independentemente da configuração de **Aplicar efetividade**.

Para produtos em que você não está usando a dimensão de produto da *versão* (sem impacto logístico nas transações), a versão não é adicionada às BOMs ou roteiros. Portanto, não haverá diferença entre as BOMs e os roteiros de versões consecutivas. Nesse caso, é altamente recomendável definir a opção **Aplicar efetividade** como *Sim*. Dessa forma, você ajuda a evitar que versões de engenharia se sobreponham e também pode ativar a BOM e o roteiro de uma versão mais recente sem precisar primeiro desativar a BOM e o roteiro da versão anterior. Se você definir a opção **Aplicar efetividade** como *Sim* neste caso, deverá desativar manualmente as BOMs e os roteiros de versões mais antigas antes de ativar a versão mais recente.
