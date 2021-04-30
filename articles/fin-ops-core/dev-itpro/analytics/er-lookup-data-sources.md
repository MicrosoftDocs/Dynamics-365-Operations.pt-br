---
title: Configurar fontes de dados de pesquisa para usar parâmetros específicos do aplicativo ER
description: Este tópico explica como configurar fontes de dados de pesquisa em formatos de relatório eletrônico (ER) para usar parâmetros especificados específicos de aplicativo ER.
author: NickSelin
manager: AnnBe
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 542580c859759c25da84589ec82495eb72bbcbe5
ms.sourcegitcommit: 74f5b04b482b2ae023c728e0df0eb78305493c6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853512"
---
# <a name="configure-lookup-data-sources-to-use-er-application-specific-parameters"></a>Configurar fontes de dados de pesquisa para usar parâmetros específicos do aplicativo ER 

[!include[banner](../includes/banner.md)]

O recurso de parâmetros específicos do aplicativo de [Relatório Eletrônico (ER)](general-electronic-reporting.md) permite que você configure a filtragem de dados em um formato de ER de forma que se baseie em um conjunto de regras abstratas. Esse conjunto de regras pode ser configurado para usar a fonte de dados do tipo **Pesquisa** que está disponível em um formato de ER. Você pode especificar regras reais além de designers de componentes de ER usando a interface de usuário (IU) que é gerada automaticamente com base nas configurações da fonte de dados de **Pesquisa** do formato de ER correspondente e nos dados da entidade legal atual. Por fim, as regras especificadas serão acessadas pela fonte de dados de **Pesquisa** do formato de ER quando esse formato for executado.

> [!NOTE]
> Use as fontes de dados configuradas do formato de ER editável para especificar quais dados de aplicativo são usados para configurar regras reais.

Use o [Designer de operações ER](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) para colocar uma fonte de dados do tipo de **Pesquisa** no formato de ER. A fonte de dados deve ser configurada para descrever a aparência de regras abstratas, incluindo o seguinte:

   - O conjunto de parâmetros de certos tipos de dados cujo valor é fornecido para especificar uma única regra.
   - O tipo de valor de certo tipo de dados que é retornado por uma única regra quando essa regra é considerada a mais apropriada entre outras.

Você pode configurar os seguintes tipos de fonte de dados de **Pesquisa**, dependendo do tipo de valor retornado por qualquer regra configurada:

   - Use o tipo **Modelo de dados\Pesquisa** quando for necessário retornar um valor de enumeração de modelo.
   - Use o tipo **Dynamics 365 Operations\Pesquisa** quando for necessário retornar um valor de enumeração de aplicativo ou um valor de [tipo de dados estendido](../extensibility/extensible-edts.md)  do aplicativo.
   - Use o tipo **Enumeração de formato\Pesquisa** quando for necessário retornar um valor de enumeração de formato.

A ilustração a seguir mostra como uma enumeração de formato pode ser configurada no formato de ER de exemplo.

   ![Mostrando uma enumeração de formato como base da fonte de dados de pesquisa configurada](./media/er-lookup-data-sources-img1.gif)

A ilustração a seguir mostra os componentes de formato que foram configurados para relatar diferentes tipos de impostos em uma seção diferente de um relatório gerado.

   ![Mostrando as seções de formato para relatar diferentes tipos de impostos](./media/er-lookup-data-sources-img2.png)

A ilustração a seguir mostra como o designer de Operações ER permite a adição de uma fonte de dados do tipo **Enumeração de formato\Pesquisa**.  A fonte de dados adicionada é configurada como retorno de um valor da enumeração de formato `List of taxation levels`.

   ![Adicionando uma fonte de dados ER do tipo Enumeração de formato\Pesquisa](./media/er-lookup-data-sources-img3.gif)

A ilustração a seguir mostra como a fonte de dados adicionada está configurada para usar o campo **Código** da lista de registro **Model.Data.Tax** da fonte de dados **Modelo** como um parâmetro que deve ser especificado para cada regra configurada.

![Configurando parâmetros da fonte de dados adicionada do tipo Enumeração de formato\Pesquisa](./media/er-lookup-data-sources-img4.gif)

A fonte de dados `Model.Data.Tax` adicionada é configurada para especificar um código de imposto para cada regra configurada, acessando registros da tabela de aplicativos **TaxTable**.

   ![Análise da fonte de dados de pesquisa de única empresa do tipo Enumeração de formato\Pesquisa](./media/er-lookup-data-sources-img5.gif)

Você pode configurar as regras de pesquisa para o formato ER selecionado, usando a interface do usuário que é alinhada automaticamente com a estrutura da fonte de dados configurada. No momento, essa interface do usuário exige que, para cada regra, você especifique o valor retornado como o valor de enumeração de formato `List of taxation levels`, bem como o código de imposto como um parâmetro.

   ![Configurar as regras para a fonte de dados configurada](./media/er-lookup-data-sources-img6.gif)

A ilustração a seguir mostra como a fonte de dados `Model.Data.Summary.LevelByLookup` do tipo **Campo calculado** pode ser configurada para chamar a fonte de dados de **Pesquisa** configurada fornecendo os parâmetros necessários. Para processar essa chamada em tempo de execução, o ER passa pela lista de regras configuradas na sequência definida para localizar a primeira regra que satisfaça as condições fornecidas. Neste exemplo, esta é a regra que contém o código de imposto correspondente ao fornecido. Como resultado, a regra mais apropriada é encontrada e o valor de enumeração configurado para a regra encontrada é retornado por essa fonte de dados.

> [!NOTE]
> Uma exceção é lançada quando nenhuma regra aplicável é encontrada. Para evitar essas exceções, configure regras adicionais no final da lista de regras para manipular casos quando um valor não configurado ou nenhum valor for fornecido. Use as opções **\*Não vazio\*** e **\*Em branco\*** adequadamente.  
>
> ![Adicionar uma fonte de dados para chamar a fonte de dados de pesquisa configurada](./media/er-lookup-data-sources-img7.png)

Ao definir a opção **Interempresarial** como **Sim** para a fonte de dados de pesquisa editável, você adiciona um novo parâmetro **Empresa** obrigatório ao conjunto de parâmetros dessa fonte de dados. O valor do parâmetro **Empresa** deve ser especificado em tempo de execução quando a fonte de dados de pesquisa é chamada. Quando o código da empresa é especificado em tempo de execução, as regras configuradas para essa empresa são usadas para encontrar a regra mais apropriada e o valor correspondente é retornado. A ilustração a seguir mostra como você pode fazer isso e como o conjunto de parâmetros da fonte de dados editável é alterado.

   ![Análise da fonte de dados de pesquisa interempresarial do tipo Enumeração de formato\Pesquisa](./media/er-lookup-data-sources-img8.gif)

> [!NOTE]
> Selecione cada empresa separadamente para configurar o conjunto de regras para essa fonte de dados de pesquisa do formato ER editável. Uma exceção é lançada em tempo de execução quando a pesquisa interempresarial é chamada com o código da empresa para a qual a configuração de pesquisa não foi concluída.
>
> Certifique-se de conceder permissões para um usuário que executa o formato ER com a fonte de dados de **Pesquisa** interempresarial para acessar os dados de todas as empresas que estão no escopo dessa fonte de dados. Caso contrário, uma exceção é lançada em tempo de execução.

A partir da versão 10.0.19, os recursos estendidos das fontes de dados de **Pesquisa** estão disponíveis. Ao definir a opção **Estendida** como **Sim** para a fonte de dados de pesquisa editável, a fonte de dados de pesquisa configurada será transformada na fonte de dados estruturada que oferece os recursos adicionais para analisar o conjunto de regras configurado. A ilustração a seguir mostra essa transformação.

   ![Análise da fonte de dados de pesquisa estruturada do tipo Enumeração de formato\Pesquisa](./media/er-lookup-data-sources-img9.gif)

- O subitem de **Pesquisa** é criado como uma função para encontrar a regra mais apropriada do conjunto de regras configuráveis com base no conjunto de parâmetros fornecido.
- O subitem **IsLookupResultSet** é criado como uma função para aceitar o valor fornecido da fonte de dados de enumeração base e retornar o valor *Booliano* como **Verdadeiro** quando o conjunto de regras contém pelo menos uma regra para a qual o valor de enumeração fornecido foi configurado como um valor devolvido. Esta função retorna o valor *Booliano* como **Falso** quando não há regras configuradas para retornar o valor de enumeração fornecido.
- O subitem de **Configuração** é criado como uma função que retorna o conjunto de regras configuradas como registros de uma lista de registros. Os valores retornados e o conjunto de parâmetros das regras configuradas são apresentados em todos os registros devolvidos como campos dos tipos de dados relevantes:

    - O valor retornado é apresentado como o campo **Resultado da pesquisa**.
    - Os parâmetros configurados são apresentados como campos com nomes de parâmetros (campo **Código** neste exemplo).

Para obter mais informações sobre como configurar a fonte de dados de **Pesquisa**, consulte [Configurar formatos de ER para usar parâmetros especificados por entidade legal](er-app-specific-parameters-configure-format.md). Para saber como definir as regras de pesquisa, consulte [Configurar os parâmetros de um formato de ER por entidade legal](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar formatos ER para usar parâmetros especificados de acordo com a entidade legal](er-app-specific-parameters-configure-format.md)

[Configurar os parâmetros de um formato ER de acordo com a entidade legal](er-app-specific-parameters-set-up.md)
