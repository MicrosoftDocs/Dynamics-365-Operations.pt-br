---
title: Configurar os parâmetros de um formato de ER por entidade legal
description: Este tópico explica como configurar os parâmetros de um formato de relatório eletrônico (ER) por entidade legal.
author: NickSelin
ms.date: 10/22/2021
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
ms.openlocfilehash: 0fce566bea6340b4016e559b1f5f1764a6881e28
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675384"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Configurar os parâmetros de um formato de ER por entidade legal

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Pré-requisitos

Para concluir estas etapas, primeiro você deve concluir as etapas em [Configurar formatos ER para usar parâmetros especificados de acordo com a entidade legal](er-app-specific-parameters-configure-format.md).

Para concluir os exemplos deste tópico, você deve ter acesso ao Microsoft Dynamics 365 Finance para uma das seguintes funções:

- Desenvolvedor de relatório eletrônico
- Consultor funcional de relatório eletrônico
- Administrador do sistema

## <a name="import-er-configurations"></a>Importar configurações ER
Para importar configurações ER, siga estas etapas: 

1. Entre no seu ambiente.
2. No painel padrão, selecione **Relatório eletrônico**.
3. Selecione **Configurações de relatórios**.
4. Na instância atual do Finance, importe as configurações que você exportou do Regulatory Configuration Services (RCS) enquanto estava concluindo as etapas em [Configurar formatos ER para usar parâmetros especificados de acordo com a entidade legal](er-app-specific-parameters-configure-format.md). Siga estas etapas para cada configuração de [Relatório eletrônico (ER)](general-electronic-reporting.md) nesta ordem: modelo de dados, mapeamento de modelos e formatos.

    1. Selecione **Troca \> Carregar de um arquivo XML**.
    2. Selecione **Procurar** para selecionar o arquivo para a configuração ER necessária no formato XML.
    3. Selecione **OK**.

    A ilustração a seguir mostra as configurações que você deve ter quando terminar.

    ![Página de configurações ER.](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Configurar parâmetros para a empresa DEMF

Você pode usar a estrutura de ER para configurar parâmetros específicos do aplicativo para um formato de ER.

1. Selecione a entidade legal **DEMF**.
2. Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.
3. No Painel de Ação, na guia **Configurações**, no grupo **Parâmetros específicos do aplicativo**, selecione **Configuração**.

    ![Página de parâmetros específicos do aplicativo ER para configurar parâmetros.](./media/GER-AppSpecParms-LookupForm.PNG)

    Na página **Parâmetros específicos do aplicativo**, você pode configurar as regras para a fonte de dados **Seletor** do formato **Formato para saber como pesquisar dados de LE**.

    Se o formato de ER de base contiver várias fontes de dados do tipo **Pesquisa**, selecione a fonte de dados desejada na guia rápida **Pesquisas** antes de começar a configurar o conjunto de regras para a fonte de dados.

    Para cada fonte de dados, você pode configurar regras separadas para cada versão do formato de ER selecionado.

    O conjunto de regras inteiro para todas as fontes de dados de pesquisa que estão disponíveis na versão selecionada do formato de ER de base compõe os parâmetros específicos do aplicativo para o formato de ER.

4. Selecione a versão **1.1.1** do formato de ER.
5. Na guia rápida **Condições**, selecione **Adicionar**.
6. No campo **Código** do novo registro, selecione a seta suspensa para abrir a pesquisa.

    A pesquisa apresenta a lista de códigos de imposto para seleção. Essa lista é retornada pela fonte de dados **Model.Data.Tax** configurada no formato de ER de base. Como essa fonte dados contém o campo **Nome**, o nome de cada código de imposto aparece na pesquisa.

    ![Pesquisa do campo Código na página de parâmetros específicos do aplicativo ER.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)

7. Selecione o código de imposto **VAT19**.
8. No campo **Resultado da pesquisa** do novo registro, selecione a seta suspensa para abrir a pesquisa. A pesquisa apresenta a lista de valores para a enumeração de formato TaxationLevel para seleção.

    Observe que, se você selecionou alemão como o idioma preferencial para o usuário conectado, as etiquetas dos valores na pesquisa estarão em alemão, desde que tenham sido traduzidas no formato ER de base. Além disso, se a etiqueta de uma fonte de dados da pesquisa foi traduzida, será exibida no idioma preferencial do usuário na guia **Pesquisas**.

    ![Campo de pesquisa traduzido para alemão na página de parâmetros específicos do aplicativo ER.](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9. Selecione o valor **Tributação normal**.

    Ao adicionar esse registro, você define a seguinte regra: quando a fonte de dados de pesquisa **Seletor** for solicitada e o código de imposto **VAT19** for passado como argumento, **Tributação normal** será retornado como o nível de tributação solicitado.

10. Selecione **Adicionar** e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **InVAT19**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Tributação normal**.

11. Selecione **Adicionar** e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **VAT7**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Tributação reduzida**.

12. Selecione **Adicionar** e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **InVAT7**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Tributação reduzida**.

13. Selecione **Adicionar** e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **THIRD**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Sem tributação**.

14. Selecione **Adicionar** e siga estas etapas:

    1. No campo **Código**, selecione o código de imposto **InVAT0**.
    2. No campo **Resultado da pesquisa**, selecione o valor **Sem tributação**.

15. Selecione **Adicionar** e siga estas etapas:

    1. No campo **Código**, selecione a opção **\*Não vazio\***.
    2. No campo **Resultado da pesquisa**, selecione o valor **Outro**.

    Ao adicionar esse último registro, você define a seguinte regra: quando o código de imposto que é passado como argumento não atender a nenhuma das regras anteriores, a fonte de dados de pesquisa retornará **Outro** como o nível de tributação solicitado.

    ![Último registro adicionado na página de parâmetros específicos do aplicativo ER.](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)

16. No campo **Estado**, selecione **Concluído**.

    Quando você executa uma versão de formato de ER que tem o status **Concluído** ou **Compartilhado**, esse conjunto de regras deve estar no estado **Concluído**. Do contrário, a execução do formato de ER de base será interrompida quando o formato tentar carregar dados desse conjunto de regras enquanto a fonte de dados de pesquisa **Seletor** estiver sendo executada.

    Quando você executa uma versão do formato de ER com o status **Rascunho**, o formato de ER de base pode acessar esse conjunto de regras, independentemente do estado.

17. Selecione **Salvar**.
18. Feche a página **Parâmetros específicos do aplicativo**.

## <a name="run-the-er-format-in-the-demf-company"></a>Executar o formato de ER na empresa DEMF
Para executar o formato ER na empresa DEMF, siga estas etapas: 

1. Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.
2. No Painel de Ação, selecione **Executar**.
3. Na caixa de diálogo exibida, selecione **OK**.
4. Baixe o demonstrativo que é gerado e armazene-o localmente.

    No demonstrativo gerado, observe que o resumo do código de imposto **InVAT7** está no nível **Reduzido** e os resumos dos códigos de imposto **VAT19** e **InVA19** estão no nível **Normal**. Esse comportamento é determinado pela configuração no conjunto de regras dependente da entidade legal.

5. Acesse **Imposto \> Impostos indiretos \> Impostos \> Códigos de imposto**.
6. Selecione o código de imposto **InVAT7**.
7. No Painel de Ação, na guia **Código de imposto**, no grupo **Consultas**, selecione **Imposto lançado** para exibir informações sobre o valor de impostos e as taxas de impostos aplicadas por código de imposto.

    ![Página Imposto lançado.](./media/GER-AppSpecParms-Statement.PNG)

8. Feche a página **Imposto lançado**.

## <a name="set-up-parameters-for-the-usmf-company"></a>Configurar parâmetros para a empresa USMF
Para configurar parâmetros para a empresa USMF, conclua as seguintes etapas: 

1. Selecione a entidade legal **USMF**.
2. Acesse **Administração da organização \> Relatório eletrônico \> Configurações**.
3. Na árvore de configurações, expanda o item **Modelo para conhecer chamadas parametrizadas**, expanda o item **Formato para conhecer chamadas parametrizadas** e selecione o formato **Formato para saber como pesquisar dados de LE**.
4. No Painel de Ação, na guia **Configurações**, no grupo **Parâmetros específicos do aplicativo**, selecione **Configuração**.
5. Selecione a versão **1.1.1** do formato de ER selecionado.
6. Na guia rápida **Condições**, selecione **Adicionar**.
7. No campo **Código** do novo registro, selecione a seta suspensa para abrir a pesquisa.

    Agora a pesquisa apresenta a lista de códigos de imposto para o imposto da empresa **USMF** para seleção.

    ![Códigos de imposto para o imposto da empresa USMF.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)

8. Selecione o código de imposto **ISENTO**.
9. No campo **Resultado da pesquisa** do novo registro, selecione o valor **Sem tributação**.
10. Selecione **Adicionar**.
11. No campo **Código** do novo registro, selecione a opção **\*Não vazio\***.
12. No campo **Resultado da pesquisa** do novo registro, selecione o valor **Tributação normal**.
13. No campo **Estado**, selecione **Concluído**.
14. Selecione **Salvar**.

    ![Página de parâmetros específicos do aplicativo do ER.](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)

15. Feche a página **Parâmetros específicos do aplicativo**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Executar o formato de ER na empresa USMF
Para executar o formato ER na empresa USMF, conclua as seguintes etapas:

1. Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.
2. No Painel de Ação, selecione **Executar**.
3. Na caixa de diálogo exibida, selecione **OK**.
4. Baixe o demonstrativo que é gerado e armazene-o localmente.

    No demonstrativo gerado, observe que agora você reutilizou o mesmo formato de ER para outra entidade legal, mas sem fazer quaisquer ajustes ao formato de ER.

## <a name="reuse-legal-entitydependent-parameters"></a>Reutilizar parâmetros dependentes da entidade legal

### <a name="duplicate-existing-parameters"></a>Duplicar parâmetros existentes

#### <a name="export-parameters"></a>Exportar parâmetros
Para exportar parâmetros, conclua as seguintes etapas:

1. Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.
2. Selecione **Configurações de relatórios**.
3. Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.
4. No Painel de Ação, na guia **Configurações**, no grupo **Parâmetros específicos do aplicativo**, selecione **Configuração**.
5. Selecione a versão **1.1.1** do formato de ER.
6. No Painel de Ações, selecione **Exportar**.
7. Baixe o arquivo que é gerado e armazene-o localmente.

    Agora o conjunto configurado de parâmetros específicos do aplicativo foi exportado como arquivo XML.

#### <a name="import-parameters"></a>Importar parâmetros
Para importar parâmetros, conclua as seguintes etapas:

1. Selecione a versão **1.1.2** do formato de ER.
2. No Painel de Ações, selecione **Importar**.
3. Selecione **Sim** para confirmar que você quer substituir os parâmetros específicos do aplicativo existentes para esta versão de formato.
4. Selecione **Procurar** para localizar o arquivo contendo os parâmetros específicos do aplicativo exportados da versão **1.1.1**.
5. Selecione **OK**.

    Agora a versão **1.1.2** do formato de ER tem os mesmos parâmetros específicos do aplicativo que você configurou originalmente para a versão **1.1.1**.

##### <a name="applicability-considerations"></a>Considerações de aplicabilidade

Os parâmetros específicos do aplicativo de um formato ER são dependentes da entidade legal. Para reutilizar os parâmetros específicos do aplicativo que foram configurados para uma entidade legal em outra entidade legal, você deve exportá-los quando estiver conectado à primeira entidade legal. Em seguida, conecte-se à outra entidade legal e importe-os.

Você também pode usar esta abordagem exportar-importar para transferir parâmetros específicos do aplicativo relacionados ao formato ER que foram configurados originalmente em uma instância do Finance para outra instância do Finance.

Se você configurar parâmetros específicos do aplicativo para uma versão de um formato ER e importar uma versão mais recente do mesmo formato para a instância atual do Finance, os parâmetros específicos do aplicativo existentes não serão aplicados à versão importada, a menos que você use o recurso **Usar parâmetros específicos do aplicativo das versões anteriores de formatos ER**. Para obter mais informações, consulte a seção [Reutilizar parâmetros existentes](#reuse-existing-parameters) posteriormente neste tópico.

Quando você seleciona um arquivo para importação, a estrutura dos parâmetros específicos do aplicativo nesse arquivo é comparada com a estrutura das fontes de dados correspondentes do tipo **Pesquisa** no formato ER selecionado para importação. Por padrão, a importação é concluída somente se a estrutura de cada parâmetro específico do aplicativo corresponder à estrutura da fonte de dados correspondente no formato ER selecionado para importação. Se as estruturas não corresponderem, uma mensagem de aviso informará que não é possível concluir a importação. Se você forçar a importação, os parâmetros específicos do aplicativo existentes para o formato ER selecionado serão eliminados e você deverá configurá-los desde o início.

A partir do Dynamics 365 Finance versão 10.0.23, você pode alterar o comportamento padrão para evitar receber uma mensagem de aviso habilitando o recurso **Alinhar parâmetros específicos do aplicativo ER durante a importação** no espaço de trabalho **Gerenciamento de recursos**. Quando esse recurso está habilitado, se a estrutura dos parâmetros específicos do aplicativo importados for diferente da estrutura das fontes de dados correspondentes no formato ER de destino selecionado para importação, a importação será realizada nos seguintes casos:

- A estrutura do formato ER de destino foi alterada adicionando novas colunas de condição a qualquer fonte de dados existente do tipo **Pesquisa**. Quando a importação é concluída, os parâmetros específicos do aplicativo são atualizados. Em todos os registros importados de parâmetros específicos do aplicativo, os valores em cada coluna de condição adicionada são inicializados com o valor padrão para o [tipo de dados](er-formula-supported-data-types-primitive.md) dessa coluna.
- A estrutura do formato ER de destino foi alterada removendo algumas colunas de condição de qualquer fonte de dados existente do tipo **Pesquisa**. Quando a importação é concluída, os parâmetros específicos do aplicativo são atualizados. Em todos os registros importados de parâmetros específicos do aplicativo, os valores em cada coluna de condição removida são excluídos.
- A estrutura do formato ER de destino foi alterada adicionando novas fontes de dados do tipo **Pesquisa**. Quando a importação é concluída, as pesquisas adicionadas são acrescentadas aos parâmetros específicos do aplicativo.
- A estrutura do formato ER de destino foi alterada removendo algumas fontes de dados existentes do tipo **Pesquisa**. Quando a importação é concluída, todos os artefatos relacionados às fontes de dados do tipo **Pesquisa** que foram removidas do formato ER de destino são excluídos dos parâmetros específicos do aplicativo importados.

Quando a importação é concluída, além das alterações descritas, o estado dos parâmetros específicos do aplicativo importados é alterado para **Em andamento**. Uma mensagem de aviso informa que os parâmetros específicos do aplicativo ajustados automaticamente devem ser editados manualmente.

### <a name="reuse-existing-parameters"></a>Reutilizar parâmetros existentes

A partir do Dynamics 365 Finance versão 10.0.23, você pode reutilizar parâmetros específicos do aplicativo que foram configurados para uma versão de um formato ER ao executar uma versão superior do mesmo formato. Para fazer isso, habilite o recurso **Usar parâmetros específicos do aplicativo das versões anteriores de formatos ER** no espaço de trabalho **Gerenciamento de recursos**. Quando este recurso é habilitado e você executa uma versão de um formato ER que está tentando ler parâmetros específicos do aplicativo, o ER tenta encontrar parâmetros específicos do aplicativo que foram configurados para a versão em execução deste formato. Ou, quando não estiverem disponíveis, para a versão anterior mais próxima deste formato.

> [!NOTE]
> Você pode reutilizar parâmetros específicos do aplicativo somente no escopo da entidade legal atual.
>
> Um erro é exibido no runtime quando você executa uma versão posterior de um formato ER que está tentando reutilizar parâmetros específicos do aplicativo que foram configurados para uma versão anterior do mesmo formato e a estrutura de pelo menos uma fonte de dados do tipo **Pesquisa** na versão de formato posterior foi alterada.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relacionamento entre parâmetros específicos do aplicativo e um formato de ER

O relacionamento entre um formato de ER e seus parâmetros específicos do aplicativo é estabelecido pelo código de identificação exclusivo e independente da instância do formato de ER. Portanto, quando você remove um formato de ER do Finance, os parâmetros específicos do aplicativo configurados para o formato de ER são mantidos na instância atual do Finance. Eles podem ser acessados quando o formato ER de base é reimportado para esta instância do Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Acessar parâmetros específicos do aplicativo usando a estrutura de ER

No exemplo anterior, você acessou parâmetros específicos do aplicativo de um formato de ER usando a estrutura de ER. Esta abordagem não permite restringir o acesso aos parâmetros específicos do aplicativo de um determinado formato de ER. Se você tiver que aplicar essas limitações, siga estas etapas. 

1. Reutilize um item de menu **ERSolutionAppSpecificParametersDesigner** existente ou implemente seu próprio item de menu **ERSolutionAppSpecificParametersDesigner**.

    ![Exibição do item de menu de ERSolutionAppSpecificParametersDesigner.](./media/GER-AppSpecParms-LookupForm-Access1.PNG)

2. Siga uma destas etapas:

    1. Crie um novo botão de item de menu e vincule-o ao registro correspondente da tabela **ERSolutionTable** definindo a propriedade **Fonte de dados** como **ERSolutionTable**.

        ![Exibição de novas configurações de item de menu.](./media/GER-AppSpecParms-LookupForm-Access2.PNG)

    2. Crie um botão simples e substitua o método **Clicked** conforme mostrado no exemplo a seguir.

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
