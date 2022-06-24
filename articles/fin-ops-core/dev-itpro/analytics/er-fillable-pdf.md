---
title: Criar configurações de ER a serem preenchidas em modelos de PDF
description: Este artigo fornece informações sobre como criar um formato de relatório eletrônico (ER) para preencher um modelo PDF.
author: NickSelin
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: ef9b650e9b676d79af8839c08cfbb1000a5aee5f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908580"
---
# <a name="design-er-configurations-to-fill-in-pdf-templates"></a>Criar configurações de ER a serem preenchidas em modelos de PDF

[!include[banner](../includes/banner.md)]

Os procedimentos neste artigo são exemplos que mostram como um usuário na função **Administrador do sistema** ou **Desenvolvedor de relatório eletrônico** pode configurar um formato de relatório eletrônico (ER) que gera relatórios como arquivos PDF usando documentos PDF preenchíveis como modelos de relatório. Essas etapas podem ser executadas em qualquer empresa do Dynamics 365 Finance ou de Regulatory Configuration Services (RCS).

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, você deve ter um dos seguintes tipos de acesso, dependendo do serviço usado para concluir os procedimentos deste artigo:

- Acesso ao Finance para uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

- Acesso ao RCS para uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

Você também deve concluir o procedimento [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

Por fim, baixe os seguintes arquivos.

| Descrição do conteúdo                       | Nome do arquivo                                     |
|-------------------------------------------|-----------------------------------------------|
| Modelo da primeira página do relatório | [IntrastatReportTemplate1.pdf](https://download.microsoft.com/download/0/8/3/0832c82b-4448-4562-afbf-01e0efc8d999/IntrastatReportTemplate1.pdf)                  |
| Modelo de outras páginas do relatório    | [IntrastatReportTemplate2.pdf](https://download.microsoft.com/download/c/7/a/c7a8a806-2192-4034-9052-e8b84b527d5e/IntrastatReportTemplate2.pdf)                  |
| Exemplo de formato ER - PDF                          | [Intrastat report (PDF).version.1.1.xml](https://download.microsoft.com/download/a/8/7/a87aea3e-3f60-404c-8899-c471d20e7ea9/IntrastatreportPDFversion1.1.xml)        |
| Exemplo de formato ER - Excel                          | [Intrastat (import from Excel).version.1.1.xml](https://download.microsoft.com/download/a/2/c/a2c0c145-d989-4e55-9d47-9647c02e4ee4/IntrastatimportfromExcelversion1.1.xml) |
| Exemplo de conjunto de dados                            | [Exemplo de dados do intrastat.xlsx](https://download.microsoft.com/download/9/f/1/9f1c5b96-3800-475f-8cf6-1ddd42873758/Intrastatsampledata.xlsx)                    |

## <a name="design-the-format-configuration"></a>Criar a configuração de formato

### <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Obter acesso à lista de configurações fornecidas pela Microsoft

1. Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.
2. Verifique se o provedor **Litware, Inc.** está disponível e marcado como ativo.
3. No bloco do provedor **Microsoft**, selecione **Repositórios**.

    > [!NOTE]
    > Se um repositório do tipo **LCS** já existir, ignore as etapas restantes deste procedimento.

4. Selecione **Adicionar**.
5. Na caixa de diálogo suspensa, no grupo do campo **Tipo de configuração do repositório**, selecione a opção **LCS**.
6. Selecione **Criar repositório**.
7. Selecione **OK**.

### <a name="get-the-model-configurations-provided-by-microsoft"></a>Obter as configurações do modelo fornecidas pela Microsoft

1. No lado esquerdo da página **Repositórios de configuração**, selecione o botão **Mostrar filtros** (o símbolo em forma de funil).
2. Adicione um filtro para um valor de **LCS** no campo **Tipo** e use o operador **começa com**.
3. Selecione **Aplicar**.
4. Selecione **Abrir**.
5. Na árvore, selecione **Módulo intrastat**.
6. Na Guia Rápida **Versões**, selecione a versão **1**.

    > [!NOTE]
    > Se o botão **Importar** na Guia Rápida **Versões** não estiver disponível, ignore as etapas restantes deste procedimento.

7. Selecione **Importar**.
8. Selecione **Sim** para confirmar a importação da versão selecionada da configuração do modelo **Módulo intrastat**.

### <a name="create-a-new-format-configuration"></a>Criar uma nova configuração de formato

1. No espaço de trabalho **Relatório eletrônico**, selecione o bloco **Configurações de relatórios**.
2. Na árvore, selecione **Módulo intrastat**.
3. Selecione **Criar configuração**.

    > [!NOTE]
    > Se o botão **Criar configuração** não estiver disponível, você deve ativar o modo de design na página **Parâmetros de relatório eletrônico**, que pode ser aberta usando o espaço de trabalho **Relatório eletrônico**.

4. Na caixa de diálogo suspensa, no grupo do campo **Novo**, selecione a opção **Formato baseado no modelo de dados intrastat**.
5. No campo **Nome**, insira **Relatório intrastat (PDF)**.
6. No campo **Descrição**, insira **Relatório intrastat no formato PDF**.

    > [!NOTE]
    > O provedor de configuração ativo é automaticamente inserido. Este provedor será capaz de manter essa configuração. Embora outros provedores possam usar essa configuração, eles não poderão mantê-la.

7. Opcional: no campo **Tipo de formato**, você pode selecionar um formato específico de documento eletrônico. Se você selecionar **PDF**, em tempo de design, o Designer de operações do ER oferecerá apenas os elementos de formato que são aplicáveis apenas aos documentos gerados no formato PDF (**PDF\Arquivo**, **PDF\Fusão de PDFs** etc.). Se você deixar este campo em branco, um formato de documento eletrônico será especificado em tempo de design no Designer de operações do ER quando um primeiro elemento de formato for adicionado. Por exemplo, se você adicionar o **Excel\Arquivo** como o primeiro elemento de formato, o Designer de operações do ER oferecerá apenas os elementos de formato que são aplicáveis apenas aos documentos gerados no formato do Excel (**Excel\Célula**, **Excel\Intervalo** etc.). formato.
8. Selecione **Criar configuração**.

Uma nova configuração de formato ER é criada. Você pode usar a versão de rascunho dessa configuração para armazenar o componente de formato ER projetado para gerar documentos eletrônicos em formato PDF.

### <a name="design-the-format-of-an-electronic-document"></a>Projetar o formato de um documento eletrônico

Em seguida, na configuração do formato ER que você criou, você criará o formato ER que gera o relatório **Controle intrastat** em formato PDF. A primeira página deste relatório deve mostrar um resumo do relatório e detalhes das transações de comércio exterior que são relatadas. As outras páginas devem mostrar apenas detalhes das transações de comércio exterior que são relatadas. Como as páginas do relatório que são geradas devem ter layouts diferentes, dois modelos diferentes no formato PDF serão usados no formato ER.

Em qualquer visualizador de PDF, abra os modelos PDF que você baixou. Observe que cada modelo contém vários campos que devem ser preenchidos. Em cada modelo, os detalhes das transações de comércio exterior são apresentados como 42 linhas, cada uma com nove campos. O número da linha aparece no final do nome de cada campo (por exemplo, **Data 1**…**Data 42** e **Mercadoria 1**…**Mercadoria 42**).

A ilustração a seguir mostra o modelo PDF da primeira página do relatório.

![Modelo 1.](media/rcs-ger-filloutpdf-template1.png)

A ilustração a seguir mostra o modelo PDF para outras páginas do relatório.

![Modelo 2.](media/rcs-ger-filloutpdf-template2.png)

1. Na página **Configurações**, selecione **Designer**.
2. Selecione **Adicionar raiz**.
3. Na caixa de diálogo suspensa, na árvore, selecione **PDF \> Fusão de PDFs**.

    Quando você seleciona o elemento **Fusão de PDFs** como o elemento raiz do formato, todos os documentos PDF gerados no tempo de execução serão mesclados em um único documento PDF final. Se você precisar de apenas um modelo de PDF para gerar todos os documentos necessários usando o formato ER criado por você, será possível selecionar **Arquivo PDF** como elemento raiz.

4. No campo **Nome**, digite **Saída**.
5. No campo **Preferências de idioma**, selecione **Preferência do usuário**. O relatório será gerado no idioma de preferência do usuário que o executa.
6. No campo **Preferências de cultura**, selecione **Preferência do usuário**. Os valores e datas apresentados nas páginas do relatório serão formatados com base no local preferido do usuário que executa o relatório.
7. Selecione **OK**.
8. No Painel de Ação, na guia **Importar**, selecione **Importar a partir do PDF**.

    Quando um documento PDF preenchível é importado como um modelo para esse formato ER, todos os elementos necessários do formato ER (elementos **Arquivo PDF**, **Grupo de campos** e **Campo**) são criados automaticamente no formato projetado, com base na estrutura do documento PDF que é importado.

9. Selecione **Procurar**. Navegue e selecione o arquivo **IntrastatReportTemplate1.pdf** que você baixou anteriormente como um pré-requisito.
10. Selecione **OK**.

    O arquivo selecionado é carregado e o campo **Modelo** na caixa de diálogo **Importar a partir do PDF** é preenchido.

11. Defina a opção **Campos do grupo** como **Sim**. Se o documento PDF selecionado contiver algum grupo de campos, eles serão usados para agrupar os elementos do formato ER criados. Um elemento de formato **Grupo de campos** será criado com essa finalidade.

    Se essa opção for configurada como **Não**, os elementos de formato ER necessários serão criados como uma lista simples de elementos aninhados no elemento de formato **Arquivo PDF** criado.

12. Selecione **OK**.

    ![Caixa de diálogo Importar a partir do PDF.](media/rcs-ger-filloutpdf-importtemplate.png)

13. Na árvore, expanda **Saída**.

    Observe que o componente **Arquivo PDF** foi criado automaticamente para gerenciar a criação da primeira página do relatório que é gerada no tempo de execução.

14. Na árvore, expanda **Saída \> Arquivo PDF**.

    Observe que a lista estruturada de elementos de formato foi criada automaticamente nesse formato ER, com base na estrutura do documento PDF preenchível que você importou anteriormente.

15. Na árvore, selecione **Saída \> Arquivo PDF**.
16. No campo **Nome**, digite **Página 1**.

    Este elemento de formato será usado para gerar a primeira página do relatório **Controle intrastat**. Essa página mostrará um resumo do relatório e detalhes das transações de comércio exterior.

    Se você deixar o campo **Preferências de idioma** em branco, a configuração **Preferências de idioma** do elemento pai **Fusão de PDFs** determinará o idioma do relatório gerado usando esse elemento de formato. Você pode selecionar outro valor para substituir a configuração do elemento pai.

    Se você deixar o campo **Preferências de cultura** em branco, a configuração **Preferências de cultura** do elemento pai **Fusão de PDFs** determinará a localidade do relatório gerado usando esse elemento de formato. A localidade determina o formato dos valores e datas nas páginas do relatório. Você pode selecionar outro valor para substituir a configuração do elemento pai.

17. No Painel de Ação, selecione a guia **Importar**. Observe que o botão **Atualizar a partir do PDF** está disponível para o elemento de formato selecionado, **Arquivo PDF**.

    Você pode usar esse botão para importar o modelo PDF atualizado para o formato editado. Quando o modelo PDF atualizado é importado, a lista de elementos de formato será alterada adequadamente:

    - Para novos campos no modelo PDF atualizado, novos elementos de formato são criados no formato ER editado.
    - Se o modelo PDF atualizado não incluir mais os campos que correspondem a qualquer elemento de formato existente no formato ER editado, esses elementos de formato serão excluídos do formato ER.

18. Na guia **Formato**, selecione **Anexos**.

    Observe que o documento PDF importado está anexado ao formato ER editado.

    ![Visualização do anexo em PDF.](media/rcs-ger-filloutpdf-attachedtemplate.png)

19. Continue a criar esse formato importando o segundo modelo PDF, adicionando as vinculações necessárias às fontes de dados e assim por diante.
20. Selecione **Salvar**.
21. Feche a página.
22. Selecione **Excluir**.
23. Selecione **Sim**.

Para saber como os novos elementos de formato **Fusão de PDFs**, **Arquivo PDF**, **Grupo de campos** e **Campo** podem ser usados para gerar documentos em formato PDF, é possível importar e analisar o exemplo de formato ER.

### <a name="import-the-format-configuration"></a>Importar a configuração de formato

Em seguida, importe o exemplo de formato ER que você baixou anteriormente para gerar o relatório **Controle intrastat** em formato PDF. A primeira página do relatório deve mostrar um resumo do relatório e detalhes das transações de comércio exterior que são relatadas. As outras páginas devem mostrar apenas detalhes das transações de comércio exterior que são relatadas.

1. Na página **Configurações**, selecione **Troca \> Carregar de um arquivo XML**.
2. Selecione **Procurar**. Navegue e selecione o arquivo **Intrastat report (PDF).version.1.1.xml** que você baixou anteriormente como um pré-requisito.
3. Selecione **OK**.

## <a name="analyze-the-format-configuration"></a>Analisar a configuração de formato

### <a name="format-layout"></a>Formato de layout

1. Na página **Configurações**, na árvore, selecione **Módulo intrastat \> Relatório intrastat (PDF)**.
2. Selecione **Designer**.
3. Selecione **Mostrar detalhes**.
4. Na árvore, expanda **Saída: Fusão de PDFs**.

    Observe que esse formato ER contém dois elementos **Arquivo PDF**, cada um dos quais usa um modelo PDF diferente. Um modelo é usado para gerar a primeira página do relatório em formato PDF e o outro modelo é usado para gerar as outras páginas.

5. Na árvore, expanda **Saída: Fusão de PDFs \> Página 1: Arquivo PDF (IntrastatReportTemplate1)**.
6. Na árvore, expanda **Saída: Fusão de PDFs \> Página N: Arquivo PDF (IntrastatReportTemplate2)**.

    Observe que, como o conteúdo dos dois modelos PDF é diferente, a estrutura dos elementos de formato aninhado para os dois elementos **Arquivo PDF** também é diferente.

### <a name="format-mapping"></a>Mapeamento de formato

1. Na página **Designer de formato**, selecione a guia **Mapeamento**.
2. Na árvore, expanda **Paginação \> Páginas**.

    ![Página do designer de fórmulas em que a árvore de modelos é expandida.](media/rcs-ger-filloutpdf-reviewformat.png)

    Observe os seguintes detalhes:

    - O elemento de formato **Saída \> Página 1** do tipo **Arquivo PDF** não está vinculado a nenhuma fonte de dados e a expressão **Habilitado** desse elemento de formato está vazia. Portanto, em tempo de execução, o modelo do PDF **IntrastatReportTemplate1** será preenchido apenas uma vez quando um documento PDF individual for gerado.
    - O elemento do formato **Saída \> Página N** do tipo **Arquivo PDF** está vinculado à fonte de dados **Paging.PageN** do tipo **Lista de Registro** e a expressão **Habilitado** deste elemento de formato está vazia. Portanto, em tempo de execução, o modelo PDF **IntrastatReportTemplate2** será preenchido para cada registro da lista de registros associados quando um documento PDF individual for gerado.
    - Como os elementos de formato **Página 1: Arquivo PDF** e **Página N: Arquivo PDF** são filhos do elemento de formato **Saída: Fusão de PDFs**, todos os documentos PDF que são preenchidos serão mesclados em um único documento PDF final.
    - As fontes de dados **Paging.Page1** e **Paging.PageN** são configuradas como filtros de registros da fonte de dados **Paging.Pages**. Essa fonte de dados é configurada para dividir todo o conjunto de transações de comércio exterior em lotes. Cada lote contém até 42 registros. A seguinte expressão ER é usada para dividir as transações em lotes:

        SPLITLIST(Totals.CommodityRecord,42)

    - A fonte de dados **Paging.Pages** contém o elemento **Paging.Pages.Enumerated** que retorna os detalhes de cada registro incluído em um lote. Esses detalhes incluem a sequência do registro no lote atual (o campo **Paging.Pages.Enumerated.Number**). O campo **Paging.Pages.Enumerated.Number** é usado na expressão **Nome** de elementos do formato **Arquivo PDF** para gerar dinamicamente um nome de campo baseado no número da transação em um lote. O nome do campo gerado é então usado para preencher o campo PDF correto no modelo PDF usado.
    - O elemento de formato **Saída \> Página N \> Detalhes 2** do tipo **Grupo PDF** está associado à fonte de dados **Paging.PageN.Enumerated** (ou **\@.Enumerated** se o modo de exibição **Caminho relativo** for usado) do tipo **Lista de registro**. Portanto, no tempo de execução, os elementos aninhados desse grupo PDF serão preenchidos para cada registro da lista de registros associados. Assim, linhas PDF individuais são virtualmente geradas para cada enésimo de 42 registros da lista **Paging.PageN.Enumerated** em que os seguintes campos PDF são preenchidos: Data N, Direção N, Mercadoria N etc. Portanto, nesse aspecto, o comportamento desse elemento de formato **Grupo de campos** se assemelha ao comportamento dos elementos de formato **XML \> Sequência** e **Texto \> Sequência**.

3. Na árvore, expanda **Saída \> Página N \> Details2**.
4. Na árvore, selecione **Saída \> Página N \> Details2 \> PageFooter**.

    Observe que o atributo **Nome** desse elemento de formato é definido como **PageFooter**. Observe também que a expressão **Nome** do elemento de formato está vazia.

5. Na árvore, selecione **Saída \> Página N \> Details2 \> Correção 1**.

    Observe que o atributo **Nome** desse elemento de formato é definido como **Correção 1**. Observe também que a expressão **Nome** do elemento de formato é definida como **Paging.FldName("Correção",\@.Número)**.

![Designer de formato onde um mapeamento é selecionado.](media/rcs-ger-filloutpdf-reviewformat2.png)

Observe que o elemento do formato **Campo** é usado para preencher um campo individual de um documento PDF preenchível que é definido como um modelo do elemento pai de formato **Arquivo PDF**. A associação do elemento de formato **Arquivo PDF** ou seus elementos aninhados, se houver elementos aninhados, especifica o valor inserido nos campos PDF correspondentes. Diferentes propriedades do elemento de formato **Campo** podem ser usadas para especificar qual campo PDF é preenchido por um elemento de formato individual:

- Na guia **Formato**, o atributo **Nome** do elemento de formato
- Na guia **Mapeamento**, a expressão **Nome** do elemento de formato

Como as duas propriedades são opcionais para um elemento do formato **Campo**, as regras a seguir são aplicadas para especificar o campo de PDF de destino:

- Se o atributo **Nome** estiver em branco e a expressão **Nome** retornar uma string vazia em tempo de execução, uma exceção será lançada em tempo de execução para notificar o usuário de que um campo PDF não pode ser encontrado no modelo PDF sendo usado para preencher o documento PDF.
- Se o atributo **Nome** estiver definido e a expressão **Nome** estiver em branco, o campo PDF com o mesmo nome do atributo **Nome** do elemento de formato será preenchido.
- Se o atributo **Nome** estiver definido e a expressão **Nome** estiver configurada, o campo PDF com o mesmo nome do valor retornado pela expressão **Nome** do elemento de formato será preenchido.

> [!NOTE]
> Quando uma caixa de seleção no modelo PDF não pertence a um grupo de caixas de seleção, ela é representada no formato ER editável como um elemento **Campo** aninhado no elemento **Arquivo PDF**. Esse tipo de caixa de seleção de PDF pode ser definido como selecionado das seguintes maneiras:
>
> - O elemento de formato **Campo** correspondente está vinculado a um campo de fonte de dados do tipo de dados *[Booliano](er-formula-supported-data-types-primitive.md#boolean)* que tem um valor de **Verdadeiro**.
> - O elemento de formato **Campo** correspondente contém um elemento de formato **Cadeia de caracteres** aninhado que é associado a um campo de fonte de dados com um valor de texto de **1**, **Verdadeiro** ou **Sim**.
>
> O modelo pode conter um grupo de caixas de seleção em que apenas uma caixa de seleção pode ser selecionada por vez. Essas caixas de seleção são representadas em um modelo PDF como vários campos de formulário do tipo *CAIXA DE SELEÇÃO*. Os campos têm o mesmo nome, mas um valor de exportação diferente. Ao importar o modelo para o formato ER editável, cada caixa de seleção será representada na estrutura hierárquica do formato como um elemento **Item do grupo de caixas de seleção** que está aninhado no mesmo elemento **Grupo de caixas de seleção**. O nome do elemento **Grupo de caixas de seleção** será igual ao nome dos campos de caixa de seleção no modelo PDF. O nome de cada elemento **Item do grupo de caixas de seleção** será igual ao valor de exportação do campo de caixa de seleção correspondente no modelo PDF.
>
> Você só pode associar um elemento **Item do grupo de caixas de seleção** a um campo de fonte de dados do tipo de dados *Booliano*.

## <a name="run-the-format-configuration"></a>Executar a configuração de formato

### <a name="import-the-format-configuration"></a>Importar a configuração de formato

Em seguida, você carregará o exemplo de formato ER **Intrastat (importar do Excel)**. Esse formato é criado para analisar uma pasta de trabalho do Microsoft Excel selecionada pelo usuário que simula transações de comércio exterior.

1. Na página **Configurações**, selecione **Troca \> Carregar de um arquivo XML**.
2. Selecione **Procurar**. Navegue e selecione o arquivo **Intrastat (importar do Excel).version.1.1.xml** que você baixou anteriormente como um pré-requisito.
3. Selecione **OK**.
4. Na árvore, selecione **Módulo intrastat \> Intrastat (importar do Excel)**.
5. Selecione **Editar**.
6. Defina a opção **Padrão do mapeamento de modelo** como **Sim**.

    > [!NOTE]
    > Se você definiu anteriormente a opção **Padrão do mapeamento de modelo** como **Sim** para a configuração **Módulo intrastat** ou outra configuração aninhada na configuração **Módulo intrastat**, defina essa opção como **Não**.

    Quando a opção **Padrão do mapeamento de modelo** é definida como **Sim**, o formato ER importado **Intrastat (importar do Excel)** é atribuído como fonte de dados padrão para a configuração de formato **Relatório intrastat (PDF)**. Assim, quando a configuração do formato **Relatório intrastat (PDF)** for executada, o conteúdo da pasta de trabalho do Excel que é analisada pelo formato ER **Intrastat (importar do Excel)** simulará transações de comércio exterior que devem ser relatado. A ilustração a seguir mostra um exemplo de uma pasta de trabalho do Excel.

    ![Pasta de trabalho do Excel que possui dados de amostra.](media/rcs-ger-filloutpdf-excelworkbook.png)

### <a name="run-the-format-configuration"></a>Executar a configuração de formato

1. Na página **Configurações**, na árvore, selecione **Módulo intrastat \> Relatório intrastat (PDF)**.
2. Selecione **Executar**.
3. Selecione **Procurar**. Navegue e selecione o arquivo **Exemplo de dados do intrastat.xlsx** que você baixou anteriormente como um pré-requisito.
4. Selecione **OK**.
5. No campo **Direção do relatório**, selecione **Ambos** para preencher todas as transações da pasta de trabalho do Excel importada no relatório PDF gerado.
6. Selecione **OK**.
7. Revise o documento PDF gerado.

A ilustração a seguir mostra um exemplo da primeira página do relatório gerado.

![Primeira página do relatório gerado.](media/rcs-ger-filloutpdf-generatedreport.png)

A ilustração a seguir mostra um exemplo de outra página do relatório que é gerado.

![Outra página do relatório gerado.](media/rcs-ger-filloutpdf-generatedreport2.png)

## <a name="limitations"></a>Limitações

Os nomes dos campos preenchíveis devem ser exclusivos no formulário PDF que você pretende usar como um modelo de relatório. Para cada campo, um elemento de formato individual com o nome correspondente é criado no formato ER editável quando um formulário PDF é importado. Se um formulário PDF contiver vários campos com o mesmo nome, um único elemento de formato será criado para não permitir que eles sejam individualmente preenchidos no tempo de execução.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="when-i-run-the-er-format-to-generate-a-report-in-pdf-format-why-do-i-get-the-following-errors--cannot-handle-iref-streams-the-current-implementation-of-pdfsharp-cannot-handle-this-pdf-feature-introduced-with-acrobat-6-and-a-pdf-name-must-start-with-a-slash-"></a>Quando executo o formato ER para gerar um relatório no formato PDF, por que obtenho os seguintes erros:  **Não é possível manipular fluxos iref. A implementação atual do PDFSharp não pode tratar esse recurso PDF apresentado com o Acrobat 6.** e **Um nome PDF deve começar com uma barra (/).**

A estrutura ER usa a versão 1.5 da biblioteca PDFSharp para gerar esses relatórios PDF. Alguns recursos do PDF 1.5 (Adobe Reader 6.0) ainda não foram implementados nesta biblioteca. Portanto, o PDFSharp ainda não pode abrir alguns arquivos marcados como **para PDF 1.5 ou posterior** e isso pode resultar em erros. Use uma das seguintes soluções para resolver o problema:

-   Ao usar seu próprio modelo PDF: faça downgrade do modelo para uma versão anterior do Adobe e comece a usar um novo modelo no formato ER.
-   Ao usar um modelo de formato ER que foi compartilhado com você por outro provedor de configuração como parte de uma solução ER: contate o proprietário desta solução de ER e forneça uma descrição do problema.
-   Ao usar a solução de ISV que contém uma versão anterior da biblioteca PDFSharp: contate o proprietário da solução e sugira uma atualização para a versão de PDFSharp mais recente.

## <a name="additional-resources"></a>Recursos adicionais

- [ER Projetar uma configuração para gerar relatórios no formato OPENXML (Novembro de 2016)](tasks/er-design-reports-openxml-2016-11.md)
- [Criar configurações de ER para gerar relatórios no formato do Word](tasks/er-design-configuration-word-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
