---
title: Configurar formatos de ER para usar parâmetros especificados por entidade legal
description: Este tópico explica como configurar formatos de relatório eletrônico (ER) para usar parâmetros especificados por entidade legal.
author: NickSelin
ms.date: 03/24/2021
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
ms.openlocfilehash: 16eab3ffa7d4a780ec9709f5c8a5c263b1e75365
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751169"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a>Configurar formatos de ER para usar parâmetros especificados por entidade legal

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Visão geral

Em muitos dos formatos de relatório eletrônico (ER) que você criará, é preciso filtrar dados usando um conjunto de valores que são específicos de cada entidade legal da sua instância (por exemplo, um conjunto de códigos de imposto para filtrar as transações de imposto). Atualmente, quando a filtragem deste tipo é configurada em um formato de ER, os valores que dependem da entidade legal (por exemplo, códigos de imposto) são usados em expressões do formato de ER para especificar regras de filtragem de dados. Portanto, o formato de ER torna-se específico da entidade legal e, para gerar os relatórios necessários, você deve criar cópias derivadas do formato de ER original para cada entidade legal onde precisa executar o formato de ER. Cada formato de ER derivado deve ser editado para ter valores específicos da entidade legal, passar por uma troca de base sempre que a versão original (base) for atualizada, exportada de um ambiente de teste e importada para um ambiente de produção quando tiver de ser implantada para uso em produção e assim por diante. Portanto, a manutenção desse tipo de solução de ER configurada é bastante complexa e demorada por vários motivos:

-   Quanto mais entidades legais existem, maior é a necessidade de manter as configurações do formato de ER.
-   A manutenção das configurações de ER requer que os usuários empresariais tenham conhecimento de ER.

O recurso de parâmetros específicos do aplicativo de ER permite que os usuários avançados configurem a filtragem de dados em um formato de ER de forma que ela seja baseada em um conjunto de regras abstratas Esse conjunto de regras pode ser configurado para usar as fontes de dados disponíveis em um formato de ER. Os usuários empresariais podem então especificar regras reais além da estrutura de ER usando a interface de usuário (UI) que é gerada automaticamente com base nas configurações do formato de ER correspondente e nos dados da entidade legal atual que serão acessados pelas fontes de dados do formato de ER. O conjunto de regras que é especificado para um formato de ER pode ser exportado de entidade legal atual da instância do Dynamics 365 Finance (Finance). Ele pode ser importado para outra entidade legal da mesma instância do Finance ou de outra instância como um conjunto de regras para o mesmo formato de ER.

## <a name="prerequisites"></a>Pré-requisitos

Para concluir os exemplos neste tópico, você deve ter acesso à instância de Regulatory Configuration Services (RCS) que foi provisionada para o mesmo locatário de Finance para uma das seguintes funções:

- Desenvolvedor de relatório eletrônico
- Consultor funcional de relatório eletrônico
- Administrador do sistema

Recomendamos que você conclua as etapas no tópico [Suporte a chamadas parametrizadas de fontes de dados de ER do tipo CAMPO CALCULADO](er-calculated-field-type.md). Se você já concluiu essas etapas, ignore as etapas na seção **Importar configurações de ER para o RCS** a seguir.

## <a name="import-er-configurations-into-rcs"></a>Importar configurações de ER para o RCS

Baixe e armazene localmente as seguintes configurações ER.

| **Descrição do conteúdo**                        | **Nome do arquivo**                                        |
|------------------------------------------------|------------------------------------------------------|
| Exemplo de arquivo de configuração **Modelo de dados de ER**    | [Modelo para conhecer chamadas parametrizadas.versão.1.xml](https://download.microsoft.com/download/2/d/b/2db913a0-3622-494e-91a2-97fc494af9b9/Modeltolearnparameterizedcalls.version.1.xml)     |
| Exemplo de arquivo de configuração **Metadados de ER**      | [Metadados para conhecer chamadas parametrizadas.versão.1.xml](https://download.microsoft.com/download/1/b/3/1b343968-5a47-4000-b5a8-6487698ef4c0/Metadatatolearnparameterizedcalls.version.1.xml)  |
| Exemplo de arquivo de configuração **Mapeamento de modelos de ER** | [Mapeamento para conhecer chamadas parametrizadas.versão.1.1.xml](https://download.microsoft.com/download/8/6/6/866e0ab6-2e05-4d98-9d52-d2da2038f6e4/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Exemplo de configuração **Formato de ER**             | [Formato para conhecer chamadas parametrizadas.versão.1.1.xml](https://download.microsoft.com/download/e/3/9/e392eadc-b9b4-4834-95c3-b8066dd00b9c/Formattolearnparameterizedcalls.version.1.1.xml)  |

Em seguida, entre em sua instância do RCS.

Neste exemplo, você irá criar uma configuração para a empresa de exemplo Litware, Inc. Para concluir este procedimento, você deve concluir as etapas descritas no tópico [Criar um provedor de configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md) no RCS.

1.  No painel padrão, selecione **Relatório eletrônico**.
2.  Selecione **Configurações de relatórios**.
3.  Importe as configurações de ER baixadas anteriormente para o RCS na seguinte ordem: modelo de dados, metadados, mapeamento de modelos e formato. Para cada configuração de ER, siga estas etapas:

    1.  Selecione **Taxa de câmbio**.
    2.  Selecione **Carregar do arquivo XML**.
    3.  Selecione **Procurar** para selecionar o arquivo para a configuração de ER necessária no formato XML.
    4.  Selecione **OK**.

## <a name="review-the-er-solution-that-is-provided"></a>Revisar a solução de ER que é fornecida

1.  Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.
2.  Selecione o item **Formato para conhecer chamadas parametrizadas**.
3.  Selecione **Designer**.
4.  Selecione **Expandir/Recolher**.

    O formato de ER **Formato para conhecer chamadas parametrizadas** gera uma obrigação fiscal no formato XML apresentando vários níveis de tributação (normal, reduzido e nenhum.) Cada nível tem um número diferente de detalhes.

    ![Vários níveis do formato ER, Formato para conhecer chamadas parametrizadas](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  Na guia **Mapeamento**, expanda os itens **Modelo**, **Dados** e **Resumo**.

    A fonte de dados **Model.Data.Summary** retorna a lista de transações de imposto. Essas transações são resumidas por código de imposto. Para essa fonte de dados, o campo calculado **Model.Data.Summary.Level** foi configurado para retornar o código do nível de tributação de cada registro resumido. Para qualquer código de imposto que pode ser recuperado da fonte de dados **Model.Data.Summary** em tempo de execução. o campo calculado retorna o código do nível de tributação (**Normal**, **Reduzido**, **Nenhum** ou **Outro**) como um valor de texto. O campo calculado **Model.Data.Summary.Level** é usado para filtrar registros da fonte de dados **Model.Data.Summary** e inserir os dados filtrados em cada elemento XML que representa um nível de tributação usando os campos **Model.Data2.Level1**, **Model.Data2.Level2** e **Model.Data2.Level3**.

    ![A lista da fonte de dados Model.Data.Summary de transações de imposto](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    O campo calculado **Model.Data.Summary.Level** foi configurado para conter uma expressão de ER. Observe que os códigos de imposto (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD** e **InVAT0**) são embutidos em código nesta configuração. Portanto, esse formato de ER depende da entidade legal onde esses códigos de imposto foram configurados.

    ![O campo Model.Data.Summary.Level calculado com códigos de imposto codificados](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    Para dar suporte a um conjunto de códigos de imposto diferente para cada entidade legal, você deve seguir estas etapas:

    - Criar uma versão derivada do formato de ER para cada entidade legal.
    - Atualize os códigos de imposto no campo calculado **Model.Data.Summary.Level** com base na configuração da entidade legal.

6.  Feche a página **Designer de formato**.

## <a name="create-a-derived-format"></a>Criar um formato derivado

Em seguida, use o recurso de parâmetros específicos do aplicativo de ER para dar suporte a um conjunto diferente de códigos de imposto para cada entidade legal em um único formato de ER.

1.  Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.
2.  Selecione o item **Formato para conhecer chamadas parametrizadas**.
3.  Selecione **Criar configuração**.
4.  Selecione a opção **Derivar do Nome: Formato para conhecer chamadas parametrizadas, Microsoft**.
5.  No campo **Nome**, insira **Formato para saber como pesquisar dados de LE**.
6.  Selecione **Criar configuração**.

## <a name="configure-a-derived-format"></a>Configurar um formato derivado

### <a name="add-a-format-enumeration"></a>Adicionar uma enumeração de formato

Em seguida, você adicionará uma nova enumeração de formato de ER. Os valores dessa enumeração de formato serão apresentados aos usuários empresariais, que especificarão conjuntos de códigos de imposto dependentes da entidade legal para os vários níveis de tributação usados no formato de ER.

1.  Selecione **Designer**.
2.  Selecione **Enumerações de formato**.
3.  Selecione **Adicionar**.
4.  No campo **Nome**, insira **Lista de níveis de tributação**.
5.  Selecione **Salvar**.
6.  Na guia **Valores de enumeração de formato**, selecione **Adicionar**.
7.  No campo **Nome**, insira **Tributação normal**.
8.  Selecione **Adicionar** novamente.
9.  No campo **Nome**, insira **Tributação reduzida**.
10. Selecione **Adicionar** novamente.
11. No campo **Nome**, insira **Sem tributação**.
12. Selecione **Adicionar** novamente.
13. No campo **Nome**, insira **Outro**.

    ![Novo registro na página de Enumerações de formato](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    Como os usuários empresariais podem utilizar diferentes idiomas para especificar conjuntos de códigos de imposto dependentes da entidade legal, recomendamos traduzir os valores dessa enumeração para os idiomas configurados como preferenciais para esses usuários no Finance.

14. Selecione o registro **Sem tributação** .
15. Clique no campo **Etiqueta**.
16. Selecione **Traduzir**.
17. No painel **Tradução do texto**, no campo **Id da etiqueta**, insira **LBL_LEVELENUM_NO**.
18. No campo **Texto no idioma padrão**, insira **Sem tributação**.
19. No campo **Idioma**, selecione **DE**.
20. No campo **Texto traduzido**, digite **keine Besteuerung**.
21. Selecione **Traduzir**.

    ![Extensão Tradução do texto](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. Selecione **Salvar**.
23. Feche a página **Enumerações de formato**.

### <a name="add-a-new-lookup-data-source"></a>Adicionar uma nova fonte de dados de pesquisa

Em seguida, você adicionará uma nova fonte de dados para especificar como os usuários empresariais especificarão regras dependentes da entidade legal para reconhecer o nível de tributação correto para cada registro de transação resumido.

1.  Na guia **Mapeamento**, selecione **Adicionar**.
2.  Selecione **Enumeração de formato\Pesquisa**.

    Você apenas identificou que cada regra que os usuários empresariais especificarem para reconhecimento do nível de tributação retornará um valor de uma enumeração do formato de ER. Observe que o tipo de fonte de dados **Pesquisa** pode ser acessado nos blocos **Modelo de dados** e **Dynamics 365 for Operations**, além do bloco **Enumeração de formato**. Portanto, as enumerações de modelo de dados de ER e as enumerações de aplicativo podem ser usados para especificar o tipo de valores retornados para fontes de dados desse tipo.
    
3.  No campo **Nome**, digite **Seletor**.
4.  No campo **Enumeração de formato**, selecione **Lista de níveis de tributação**.

    Você apenas especificou que, para cada regra especificada nessa fonte dados, um usuário empresarial deve selecionar um dos valores da enumeração de formato **Lista de níveis de tributação** como um valor retornado.
    
5.  Selecione **Editar pesquisa**.
6.  Selecione **Colunas**.
7.  Expanda o item **Modelo**.
8.  Expanda o item **Dados**.
9.  Expanda o item **Imposto**.
10. Selecione o item **Model.Data.Tax.Code**.
11. Selecione o botão **Adicionar** (a seta para a direita.)

    ![Extensão Colunas](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    Você apenas especificou que, para cada regra especificada nessa fonte dados para reconhecimento do nível de tributação, um usuário empresarial deve selecionar um dos códigos de imposto como uma condição. A lista de códigos de imposto que o usuário empresarial pode selecionar será retornada pela fonte de dados **Model.Data.Tax**. Como essa fonte dados contém o campo **Nome**, o nome do código de imposto será mostrado para cada valor de código de imposto na pesquisa apresentada para o usuário empresarial.
    
12. Selecione **OK**.

    ![Página do designer de pesquisa](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    Os usuários empresariais podem adicionar várias regras como registros dessa fonte de dados. Cada registro será numerado por uma linha por código. As regras serão avaliadas em ordem crescente de número de linha.

    Pelo fato de você ter selecionado o campo **Código de imposto** como uma condição para as regras nessa fonte dados de pesquisa e como o **Código de imposto** é configurado como um campo do tipo de dados **String**, cada regra será avaliada em tempo de execução comparando o código de imposto passado para a fonte de dados com o código de imposto definido nesse registro da fonte de dados.

    Quando uma regra que atende à condição configurada é encontrada, essa fonte dados retorna o valor de pesquisa da regra definido no campo **Resultados da pesquisa**. Se nenhuma regra for encontrada, será gerada uma exceção para notificar o usuário de que a fonte de dados atual não pode retornar um valor correto.

13. Selecione **Salvar**.
14. Feche a página **Designer de pesquisa**.
15. Selecione **OK**.

    Observe que você adicionou uma nova fonte de dados que retornará o nível de tributação como o valor da enumeração de formato **Lista de níveis de tributação** para qualquer código de imposto passado para a fonte de dados como argumento do parâmetro **Código** do tipo de dados **String**.
    
    ![Formatar página do designer com nova fonte de dados](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    Observe que a avaliação das regras configuradas depende do tipo de dados dos campos que foram selecionados para definir as condições dessas regras. Quando você selecionar um campo configurado como um campo de tipo de dados **Numérico** ou **Data**, os critérios serão diferentes dos critérios descritos anteriormente para o tipo de dados **String**. Para os campos **Numérico** e **Data**, a regra deve ser especificada como um intervalo de valores. A condição de regra será considerada atendida quando um valor passado para a fonte de dados estiver no intervalo configurado.
    
    A ilustração a seguir mostra um exemplo desse tipo de configuração. Além do campo **Model.Data.Tax.Code** do tipo de dados **String**, o campo **Model.Tax.Summary.Base** do tipo de dados **Real** é usado para especificar as condições para uma fonte de dados de pesquisa.
    
    ![Página do designer de pesquisa com colunas adicionais](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    Como os campos **Model.Data.Tax.Code** e **Model.Tax.Summary.Base** são selecionados para essa fonte dados de pesquisa, cada regra da fonte de dados será configurada da seguinte maneira:
    
    -   Na lista que é exibida, o valor da enumeração de formato **Lista de níveis de tributação** deve ser selecionado como um valor retornado.
    -   O código de imposto ser inserido como uma condição dessa regra. Somente os códigos de imposto fornecidos pela fonte de dados **Model.Data.Tax** são aplicáveis.
    -   Os valores mínimo e máximo do valor base do imposto devem ser inseridos como condições da regra.

    Cada regra dessa fonte de dados será avaliada da seguinte maneira em tempo de execução:
    -   O código do tipo de dados **String** que foi passado para a fonte dados é igual ao código de imposto de uma regra?
    -   O valor do tipo de dados **Real** que foi passado para a fonte de dados está entre valores mínimo e máximo especificados?

    Uma regra será considerada aplicável quando as duas condições forem satisfeitas.

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a>Traduzir a etiqueta da fonte de dados de consulta adicionada

Como os usuários empresariais podem utilizar diferentes idiomas para especificar conjuntos de códigos de imposto dependentes da entidade legal, recomendamos que você traduza a etiqueta de qualquer fonte de dados de pesquisa que adicionar para que ela seja apresentada no idioma preferencial de cada usuário na página correspondente.

1.  Selecione a fonte de dados **Model.Data.Selector**.
2.  Selecione **Editar**.
3.  Clique no campo **Etiqueta**.
4.  Selecione **Traduzir**.
5.  No painel **Tradução do texto**, no campo **Id da etiqueta**, insira **LBL_SELECTOR_DS**.
6.  No campo **Texto no idioma padrão**, insira **Selecionar nível de tributação por código de imposto**.
7.  No campo **Idioma**, selecione **DE**.
8.  No campo **Texto traduzido**, insira **Steuerebene für Steuerkennzeichen auswählen**.
9.  Selecione **Traduzir**.
10. Selecione **OK**.

    ![Extensão Propriedades da fonte de dados](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a>Adicionar um novo campo para consumir a pesquisa configurada

1.  Expanda o item **Model.Data**.
2.  Selecione o item **Model.Data.Summary**.
3.  Selecione **Adicionar**.
4.  Selecione **Funções/Campo calculado**.
5.  No campo **Nome**, insira **LevelByLookup**.
6.  Selecione **Editar fórmula**.
7.  No campo **Fórmula**, insira **Model.Selector(Model.Data.Summary.Code)**.
8.  Selecione **Salvar**.

    ![Adicionando Model.Selector(Model.Data.Summary.Code) à página do designer de fórmulas](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  Feche a página **Editor de fórmulas**.
10. Selecione **OK**.

    ![Formatar página do designer com nova fórmula adicionada](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    Observe que o campo calculado **LevelByLookup** que você adicionou retornará o nível de tributação como o valor da enumeração de formato **Lista de níveis de tributação** para cada registro resumido de transações de imposto. O código de imposto do registro será passado para a fonte de dados de pesquisa **Model.Selector** e o conjunto de regras para essa fonte de dados será usado para selecionar o nível de tributação correto.

### <a name="add-a-new-format-enumeration-based-data-source"></a>Adicionar uma nova fonte de dados com base em enumeração de formato

Em seguida, você adicionará uma nova fonte de dados que faz referência à enumeração de formato adicionada anteriormente. Os valores dessa fonte de dados serão usados posteriormente em uma expressão de formato de ER.

1.  Selecione **Adicionar raiz**.
2.  Selecione **Enumerações de formato\Enumeração**.
3.  No campo **Nome**, insira **TaxationLevel**.
4.  No campo **Enumeração de formato**, selecione **Lista de níveis de tributação**.
5.  Selecione **Salvar**.

### <a name="modify-an-existing-field-to-start-to-use-the-lookup"></a>Modificar um campo existente para começar a usar a pesquisa

Em seguida, você modificará o campo calculado existente para que ele use a fonte de dados de pesquisa configurada para retornar o valor de nível de tributação correto, dependendo do código de imposto.

1.  Selecione o item **Model.Data.Summary.Level**.
2.  Selecione **Editar**.
3.  Selecione **Editar fórmula**.

    Observe que a expressão atual do campo **Model.Data.Summary.Level** inclui os seguintes códigos de imposto codificados:
    
    CASE (@.Code, "VAT19", "Normal", "InVAT19", "Normal", "VAT7", "Reduzido", "InVAT7", "Reduzido", "THIRD", "Nenhum", "InVAT0", "Nenhum", "Outro")

4.  No campo **Fórmula**, insira **CASE(@.LevelByLookup, TaxationLevel.'Tributação normal',"Normal”, TaxationLevel.'Tributação reduzida', "Reduzido", TaxationLevel.'Sem tributação', "Nenhuma", "Outro")**.

    ![Página do designer de operação de ER](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    Observe que agora a expressão do campo **Model.Data.Summary.Level** retornará o nível de tributação com base no código de imposto do registro atual e no conjunto de regras configurado por um usuário empresarial na fonte de dados de pesquisa **Model.Data.Selector**.
    
5.  Selecione **Salvar**.
6.  Feche a página **Designer de fórmulas**.
7.  Selecione **OK**.
8.  Selecione **Salvar**.
9.  Feche a página **Designer de formato**.

## <a name="complete-the-draft-version-of-a-derived-format"></a>Concluir a versão de rascunho de um formato derivado

1.  Na FastTab **Versões**, selecione **Alterar status**.
2.  Selecione **Concluir**.
3.  Selecione **OK**.

## <a name="export-completed-version-of-modified-format"></a>Exportar a versão concluída de um formato modificado

1.  Na árvore de configuração, selecione o item **Formato para saber como pesquisar dados de LE**.
2.  Na FastTab **Versões**, selecione o registro com o status **Concluído**.
3.  Selecione **Taxa de câmbio**.
4.  Selecione **Exportar como arquivo XML**.
5.  Selecione **OK**.
6.  O navegador da Web baixa um arquivo **Formato para saber como pesquisar dados de LE.xml**. Armazene esse arquivo localmente.

Repita as etapas nesta seção para itens pai do formato **Formato para saber como pesquisar dados de LE** e armazene os seguintes arquivos localmente:

-   Formato para conhecer chamadas parametrizadas.xml
-   Mapeamento para conhecer chamadas parametrizadas.xml
-   Modelo para conhecer chamadas parametrizadas.xml

Para aprender a usar o formato de ER configurado **Formato para saber como pesquisar dados de ER** para configurar conjuntos de códigos de imposto dependentes de entidade legal a fim de filtrar transações de imposto por diferentes níveis de tributação, conclua as etapas no tópico [Configurar os parâmetros de um formato de ER por entidade legal](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Recursos adicionais

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Configurar os parâmetros de um formato de ER por entidade legal](er-app-specific-parameters-set-up.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
