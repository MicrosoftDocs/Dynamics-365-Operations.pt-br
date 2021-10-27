---
title: Configurar os parâmetros de um formato de ER por entidade legal
description: Este tópico explica como configurar os parâmetros de um formato de relatório eletrônico (ER) por entidade legal.
author: NickSelin
ms.date: 10/29/2019
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
ms.openlocfilehash: baa3cab78574ac3779aaea000f0b2b88ff625c37
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605246"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Configurar os parâmetros de um formato de ER por entidade legal

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>Pré-requisitos

Para concluir essas etapas, primeiro você deve concluir as etapas no tópico [Configurar formatos de ER para usar parâmetros especificados por entidade legal](er-app-specific-parameters-configure-format.md) .

Para concluir os exemplos deste tópico, você deve ter acesso ao Microsoft Dynamics 365 Finance (Finance) para uma das seguintes funções:

- Desenvolvedor de relatório eletrônico
- Consultor funcional de relatório eletrônico
- Administrador do sistema

## <a name="import-er-configurations"></a>Importar configurações de ER

1.  Entre no seu ambiente.
2.  No painel padrão, selecione **Relatório eletrônico**.
3.  Selecione **Configurações de relatórios**.
4.  Importe para a instância atual do Finance as configurações que exportou do Regulatory Configuration Services (RCS) enquanto estava concluindo as etapas no tópico [Configurar formatos de ER usar parâmetros especificados por entidade legal](er-app-specific-parameters-configure-format.md). Siga estas etapas para cada configuração de relatório eletrônico (ER), nesta ordem: modelo de dados, mapeamento de modelos e formatos.

    1. Selecione **Troca \> Carregar de um arquivo XML**.
    2. Selecione **Procurar** para selecionar o arquivo para a configuração de ER necessária no formato XML.
    3. Selecione **OK**.
    
    A ilustração a seguir mostra as configurações que você deve ter quando terminar.

    ![Página de configurações de ER.](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Configurar parâmetros para a empresa DEMF

Você pode usar a estrutura de ER para configurar parâmetros específicos do aplicativo para um formato de ER.

1.  Selecione a entidade legal **DEMF**.
2.  Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.
3.  No Painel de Ação, na guia **Configurações**, no grupo **Parâmetros específicos do aplicativo**, selecione **Configuração**.
    
    Na página **Parâmetros específicos do aplicativo**, você pode configurar as regras para a fonte de dados **Seletor** do formato **Formato para saber como pesquisar dados de LE**.
    
    Se o formato de ER de base contiver várias fontes de dados do tipo **Pesquisa**, selecione a fonte de dados desejada na guia rápida **Pesquisas** antes de começar a configurar o conjunto de regras para a fonte de dados.
    
    Para cada fonte de dados, você pode configurar regras separadas para cada versão do formato de ER selecionado.
    
    O conjunto de regras inteiro para todas as fontes de dados de pesquisa que estão disponíveis na versão selecionada do formato de ER de base compõe os parâmetros específicos do aplicativo para o formato de ER.

4.  Selecione a versão **1.1.1** do formato de ER.
5.  Na guia rápida **Condições**, selecione **Adicionar**.
6.  No campo **Código** do novo registro, selecione a seta suspensa para abrir a pesquisa.

    A pesquisa apresenta a lista de códigos de imposto para seleção. Essa lista é retornada pela fonte de dados **Model.Data.Tax** configurada no formato de ER de base. Como essa fonte dados contém o campo **Nome**, o nome de cada código de imposto aparece na pesquisa.

    ![Página de parâmetros específicos do aplicativo do ER, pesquisa do campo Código.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  Selecione o código de imposto **VAT19**.
8.  No campo **Resultado da pesquisa** do novo registro, selecione a seta suspensa para abrir a pesquisa. A pesquisa apresenta a lista de valores para a enumeração de formato TaxationLevel para seleção.

    Observe que, se alemão for selecionado como o idioma preferencial do usuário conectado, as etiquetas dos valores na pesquisa estarão em alemão, uma vez que foram traduzidos no formato de ER de base. Além disso, se a etiqueta de uma fonte de dados da pesquisa foi traduzida, será exibida no idioma preferencial do usuário na guia **Pesquisas**.

    ![Parâmetros específicos do aplicativo ER, resultados da pesquisa exibidos no idioma de preferência alemão.](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  Selecione o valor **Tributação normal**.

    Ao adicionar esse registro, você define a seguinte regra: sempre que a fonte de dados de pesquisa **Seletor** for solicitada e o código de imposto **VAT19** for passado como argumento, **Tributação normal** será retornado como o nível de tributação solicitado.

10. Selecione **Adicionar** e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **InVAT19**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Tributação normal**.
    
11. Selecione **Adicionar** novamente e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **VAT7**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Tributação reduzida**.
    
12. Selecione **Adicionar** novamente e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **InVAT7**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Tributação reduzida**.
    
13. Selecione **Adicionar** novamente e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **THIRD**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Sem tributação**.
    
14. Selecione **Adicionar** novamente e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **InVAT0**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Sem tributação**.
    
15. Selecione **Adicionar** novamente e siga estas etapas:

    1. No campo **Código**, selecione a opção **\*Não vazio\***.
    2. No campo **Resultado da pesquisa**, selecione o valor **Outro**.
    
    Ao adicionar esse último registro, você define a seguinte regra: sempre que o código de imposto que é passado como argumento não atender a nenhuma das regras anteriores, a fonte de dados de pesquisa retornará **Outro** como o nível de tributação solicitado.

    ![Parâmetros específicos do aplicativo ER, FastTab Condições com o último registro de Outro.](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. No campo **Estado**, selecione **Concluído**.

    Quando você executa uma versão de formato de ER que tem o status **Concluído** ou **Compartilhado**, esse conjunto de regras deve estar no estado **Concluído**. Do contrário, a execução do formato de ER de base será interrompida quando o formato tentar carregar dados desse conjunto de regras enquanto a fonte de dados de pesquisa **Seletor** estiver sendo executada.
    
    Quando você executa uma versão do formato de ER com o status **Rascunho**, o formato de ER de base pode acessar esse conjunto de regras, independentemente do estado.
    
17. Selecione **Salvar**.
18. Feche a página **Parâmetros específicos do aplicativo**.

## <a name="run-the-er-format-in-the-demf-company"></a>Executar o formato de ER na empresa DEMF

1.  Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.
2.  No Painel de Ação, selecione **Executar**.
3.  Na caixa de diálogo exibida, selecione **OK**.
4.  Baixe a instrução que é gerada e armazene-a localmente.

    Na instrução gerada, observe que o resumo do código de imposto **InVAT7** foi colocado no nível **Reduzido** e os resumos dos códigos de imposto **VAT19** e **InVA19** foram colocados no nível **Normal**. Esse comportamento é determinado pela configuração no conjunto de regras dependente da entidade legal.
    
5.  Acesse **Imposto \> Impostos indiretos \> Impostos \> Códigos de imposto**.
6.  Selecione o código de imposto **InVAT7**.
7.  No Painel de Ação, na guia **Código de imposto**, no grupo **Consultas**, selecione **Imposto lançado** para exibir informações sobre o valor de impostos e as taxas de impostos aplicadas por código de imposto.

    ![Página Imposto lançado.](./media/GER-AppSpecParms-Statement.PNG)

8.  Feche a página Imposto lançado.

## <a name="set-up-parameters-for-the-usmf-company"></a>Configurar parâmetros para a empresa USMF

1.  Selecione a entidade legal **USMF**.
2.  Acesse **Administração da organização \> Relatório eletrônico \> Configurações**.
3.  Na árvore de configurações, expanda o item **Modelo para conhecer chamadas parametrizadas**, expanda o item **Formato para conhecer chamadas parametrizadas** e selecione o formato **Formato para saber como pesquisar dados de LE**.
4.  No Painel de Ação, na guia **Configurações**, no grupo **Parâmetros específicos do aplicativo**, selecione **Configuração**.
5.  Selecione a versão **1.1.1** do formato de ER selecionado.
6.  Na guia rápida **Condições**, selecione **Adicionar**.
7.  No campo **Código** do novo registro, selecione a seta suspensa para abrir a pesquisa.

    Agora a pesquisa apresenta a lista de códigos de imposto para o imposto da empresa **USMF** para seleção.

    ![Parâmetros específicos do aplicativo ER, pesquisa do campo Código mostrando a lista de códigos de imposto para a empresa USMF.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  Selecione o código de imposto **ISENTO**.
9.  No campo **Resultado da pesquisa** do novo registro, selecione o valor **Sem tributação**.
10. Selecione **Adicionar** novamente.
11. No campo **Código** do novo registro, selecione a opção **\*Não vazio\***.
12. No campo **Resultado da pesquisa** do novo registro, selecione o valor **Tributação normal**.
13. No campo **Estado**, selecione **Concluído**.
14. Selecione **Salvar**.

    ![Página de parâmetros específicos do aplicativo do ER.](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. Feche a página **Parâmetros específicos do aplicativo**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Executar o formato de ER na empresa USMF

1.  Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.
2.  No Painel de Ação, selecione **Executar**.
3.  Na caixa de diálogo exibida, selecione **OK**.
4.  Baixe a instrução que é gerada e armazene-a localmente.

    Na instrução gerada, observe que agora você reutilizou o mesmo formato de ER para outra entidade legal, mas sem fazer quaisquer ajustes ao formato de ER.

## <a name="reuse-legal-entitydependent-parameters"></a>Reutilizar parâmetros dependentes da entidade legal

### <a name="export-parameters"></a>Exportar parâmetros

1.  Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.
2.  Selecione **Configurações de relatórios**.
3.  Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.
4.  No Painel de Ação, na guia **Configurações**, no grupo **Parâmetros específicos do aplicativo**, selecione **Configuração**.
5.  Selecione a versão **1.1.1** do formato de ER.
6.  No Painel de Ações, selecione **Exportar**.
7.  Baixe o arquivo que é gerado e armazene-o localmente.

    Agora o conjunto configurado de parâmetros específicos do aplicativo foi exportado como arquivo XML.

### <a name="import-parameters"></a>Importar parâmetros

1.  Selecione a versão **1.1.2** do formato de ER.
2.  No Painel de Ações, selecione **Importar**.
3.  Selecione **Sim** para confirmar que você quer substituir os parâmetros específicos do aplicativo existentes para esta versão de formato.
4.  Selecione **Procurar** para localizar o arquivo contendo os parâmetros específicos do aplicativo exportados da versão **1.1.1**.
5.  Selecione **OK**.

    Agora a versão **1.1.2** do formato de ER tem os mesmos parâmetros específicos do aplicativo que você configurou originalmente para a versão **1.1.1**.
    
    Observe que os parâmetros específicos do aplicativo de um formato de ER são dependentes da entidade legal. Para reutilizar os parâmetros específicos do aplicativo que foram configurados para uma entidade legal em outra entidade legal, você deve exportá-los quando estiver conectado à primeira entidade legal e importá-los depois que se conectar à outra entidade legal.

    Você também pode usar esta abordagem para transferir parâmetros específicos do aplicativo relacionados a um formato de ER que foram configurados originalmente em uma instância do Finance para outra instância do Finance.

    Lembre-se de que, se você configurar parâmetros específicos do aplicativo para uma versão de um formato de ER e importar uma versão superior do mesmo formato para a instância atual do Finance, os parâmetros específicos do aplicativo existentes não serão aplicados para a versão importada.
    
    Lembre-se também que, quando você selecionar um arquivo para importação, a estrutura dos parâmetros específicos do aplicativo nesse arquivo é comparada com a estrutura da fonte de dados correspondente do tipo **Pesquisa** no formato de ER selecionado para importação. A importação é feita quando a estrutura de cada parâmetro específico do aplicativo corresponde à estrutura da fonte de dados correspondente no formato de ER selecionado para importação. Se as estruturas não corresponderem, você receberá uma mensagem de aviso informando que não é possível fazer a importação. Se você forçar a importação, os parâmetros específicos do aplicativos existentes para o formato de ER selecionado serão eliminados e você deverá configurá-los desde o início.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relacionamento entre parâmetros específicos do aplicativo e um formato de ER

O relacionamento entre um formato de ER e seus parâmetros específicos do aplicativo é estabelecido pelo código de identificação exclusivo e independente da instância do formato de ER. Portanto, quando você remove um formato de ER do Finance, os parâmetros específicos do aplicativo configurados para o formato de ER são mantidos na instância atual do Finance. Eles podem ser acessados sempre que o formato de ER de base for reimportado para esta instância do Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Acessar parâmetros específicos do aplicativo usando a estrutura de ER

No exemplo anterior, você acessou parâmetros específicos do aplicativo de um formato de ER usando a estrutura de ER. Esta abordagem não permite restringir o acesso aos parâmetros específicos do aplicativo de um determinado formato de ER. Se você tiver que aplicar essas limitações, siga estas etapas. 

1.  Reutilize um item de menu **ERSolutionAppSpecificParametersDesigner** existente ou implemente seu próprio item de menu **ERSolutionAppSpecificParametersDesigner**.

    ![Página do Visual Studio, painel Propriedades.](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  Siga uma destas etapas:

    1.  Crie um novo botão de item de menu e vincule-o ao registro correspondente da tabela **ERSolutionTable** definindo a propriedade **Fonte de dados** como **ERSolutionTable**.
    
        ![Página do Visual Studio, painéis de Design.](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  Crie um botão simples e substitua o método **Clicked** conforme mostrado no exemplo a seguir.
    
        Usando esta abordagem, você pode especificar um ID de solução exclusivo (definido por meio do valor **GUID**) para permitir acesso aos parâmetros específicos do aplicativo de apenas um determinado formato de ER e às cópias descendentes que são derivadas dele.
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a>Recursos adicionais

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Configurar formatos de ER para usar parâmetros especificados por entidade legal](er-app-specific-parameters-configure-format.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
