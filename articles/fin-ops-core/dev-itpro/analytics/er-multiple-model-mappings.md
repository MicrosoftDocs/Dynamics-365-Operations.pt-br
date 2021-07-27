---
title: Gerenciar vários mapeamentos derivados para uma única raiz de modelo
description: Este tópico explica como gerenciar vários mapeamentos derivados que foram configurados para uma única raiz de modelo.
author: NickSelin
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 595de6292b81ca78bf08a66f61850c3b5a537396
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354382"
---
# <a name="manage-several-derived-mappings-for-a-single-model-root"></a>Gerenciar vários mapeamentos derivados para uma única raiz de modelo

[!include [banner](../includes/banner.md)]

Um componente de [modelo](general-electronic-reporting.md) de dados de [relatório eletrônico (ER)](general-electronic-reporting.md#data-model-and-model-mapping-components) é usado em todos os componentes de [formato](general-electronic-reporting.md#FormatComponentOutbound) de ER configurados como a fonte de dados para gerar documentos de saída. Para descrever um único domínio comercial, configure um componente de modelo de dados que tenha várias definições raiz. 

Toda definição raiz permite que você represente os dados desse domínio da forma mais adequada para fins de relatório específicos. Para cada definição raiz, você pode configurar um componente de [mapeamento de modelo](general-electronic-reporting.md#data-model-and-model-mapping-components) de ER como a implementação específica do Microsoft Dynamics 365 Finance do seu modelo de dados. Dessa forma, você descreverá como o modelo de dados será preenchido no runtime.

Os componentes de mapeamento do modelo de ER podem residir nas [configurações](general-electronic-reporting.md#Configuration) do modelo de dados de ER e nas configurações de mapeamento do modelo de ER. Uma única configuração de ER pode conter muitos componentes de mapeamento, cada um deles configurado para uma única definição raiz. E uma única configuração de ER pode conter somente um componente de mapeamento que é configurado para uma única definição raiz.

Muitos provedores de configuração podem oferecer configurações de mapeamento de modelos de ER para o mesmo modelo de dados de ER. Essas configurações de mapeamento de modelos podem conter componentes de mapeamento para diferentes definições raiz. Você pode usar um mapeamento de modelo para uma definição raiz oferecida por um [provedor](general-electronic-reporting.md#Provider) e usar um mapeamento de modelo para outra definição raiz oferecida por outro provedor.

Os procedimentos deste tópico explicam como gerenciar várias configurações de mapeamento de modelos de ER de um modelo de dados de ER quando eles contêm componentes de mapeamento de modelos diferentes configurados para a mesma definição raiz. 

Para concluir os procedimentos deste tópico, você deve ter a função de Administrador do sistema ou Desenvolvedor de relatório eletrônico.

Todos os procedimentos a seguir podem ser feitos na empresa USMF. Nenhum código é necessário.

## <a name="configure-the-er-framework"></a>Configurar a estrutura de ER

Como usuário na função de Desenvolvedor de relatório eletrônico, [configure o conjunto mínimo](er-quick-start2-customize-report.md#ConfigureFramework) de parâmetros de ER antes de começar a usar a estrutura de ER para gerar documentos comerciais.

## <a name="import-the-standard-er-format-configurations"></a>Importar as configurações do formato de ER padrão

Para adicionar as configurações de ER padrão à instância atual do Finance, você deve importá-las do repositório de ER configurado para essa instância. Siga as etapas de [Baixar as configurações de ER do repositório global do serviço de configuração](er-download-configurations-global-repo.md) para importar as seguintes configurações de formato de ER:

- **Fatura de texto livre (Excel)**, version 220.106
- **Fatura do projeto (Excel)**, version 226.27

## <a name="review-the-imported-er-configurations"></a>Examinar as configurações de ER importadas

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Configurações**, selecione o título **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de fatura**.

    ![Analisar as configurações importadas na página Configurações.](./media/er-multiple-model-mappings-image1.png)

4. Analise o formato **Fatura de texto livre (Excel)**:

    1. Na árvore de configuração no painel esquerdo, selecione **Fatura de texto livre (Excel)**.
    2. No Painel de Ação, selecione **Designer**.
    3. Na página **Designer de formato**, na guia **Mapeamento**, na lista de fontes de dados, selecione **Modelo**.
    4. Selecione **Exibir**.
    
       O formato de ER atual é configurado para usar a definição raiz **InvoiceCustomer** do **Modelo de fatura**. Quando esse formato é executado e a fonte de dados **Modelo** é chamada, o mapeamento do modelo configurado para a definição raiz **InvoiceCustomer** é usado para acessar os dados do aplicativo e preencher o modelo de dados.

        ![Revisar a fonte de dados do modelo na página Designer de formato.](./media/er-multiple-model-mappings-image2.png)

    6. Feche a página **Designer de formato**.

5. Revise o conteúdo da configuração **Mapeamento de modelo de fatura**:

    1. Na árvore de configuração no painel esquerdo, selecione **Mapeamento de modelo de fatura**.
    2. No Painel de Ação, selecione **Designer**.
    3. Na página **Modelo para mapeamento de fonte de dados**, observe que a configuração de mapeamento do modelo de ER atual contém vários componentes de mapeamento de modelos:

        + O mapeamento de modelo **Fatura de cliente** é configurado para a definição raiz **InvoiceCustomer** do **Modelo de fatura**. Portanto, quando o formato de ER **Fatura de texto livre (Excel)** é executado, o mapeamento de modelo **Fatura de cliente** dessa configuração de ER pode ser escolhido para acessar dados de aplicativos e preencher o modelo de dados.
        + O mapeamento de modelo **Fatura de projeto** é configurado para a definição raiz **InvoiceProject** do **Modelo de fatura**. Portanto, quando o formato de ER **Fatura de projeto (Excel)** é executado, o mapeamento de modelo **Fatura de projeto** dessa configuração de ER pode ser escolhido para acessar dados de aplicativos e preencher o modelo de dados.

        ![Mapeamento de modelo de fatura na página Mapeamento de modelo para fonte de dados.](./media/er-multiple-model-mappings-image3.png)

    4. Feche a página **Modelo para mapeamento de fonte de dados**.
    5. Na guia rápida **Versões**, selecione **Excluir** para excluir todas as versões da configuração de ER posteriores à versão 240.175.

6. Revise o conteúdo da configuração do **Mapeamento de modelo de fatura (RDP)**:

    1. Na árvore de configuração no painel esquerdo, selecione **Mapeamento de modelo de fatura de projeto (RDP)**.
    2. No Painel de Ação, selecione **Designer**.
    3. Na página **Mapear o mapeamento de fonte de dados**, observe que a configuração de mapeamento do modelo de ER atual contém o mapeamento de modelo **nvoiceProject** e que esse mapeamento de modelo está configurado para a definição raiz **InvoiceProject** do **Modelo de fatura**. Quando o formato de ER **Fatura de projeto (Excel)** é executado, selecione o mapeamento de modelo **InvoiceProject** dessa configuração de ER para acessar dados de aplicativos e preencher o modelo de dados.

        ![Mapeamento de modelo de fatura de projeto na página Mapeamento de modelo para fonte de dados.](./media/er-multiple-model-mappings-image4.png)

    4. Feche a página **Modelo para mapeamento de fonte de dados**.
    5. Na guia rápida **Versões**, selecione **Excluir** para excluir todas as versões da configuração de ER posteriores à versão 226.35.

## <a name="customize-the-imported-er-configurations"></a>Personalizar as configurações de ER importadas

Esta seção explica como [personalizar](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration) os mapeamentos de modelo fornecidos pela Microsoft. Por exemplo, a personalização pode ser necessária para implementar a lógica personalizada ou adicionar associações ausentes.

### <a name="customize-the-invoice-model-mapping-configuration"></a>Personalizar a configuração do mapeamento de modelo de fatura

1. Na página **Configurações**, na árvore de configuração no painel esquerdo, selecione **Mapeamento de modelo de fatura**.
2. No Painel de Ações, selecione **Criar configuração**.
3. Na caixa de diálogo suspensa **Criar configuração**, no campo **Novo**, selecione **Derivar do Nome: mapeamento de modelo de fatura, Microsoft**.
4. No campo **Nome**, insira **Mapeamento de modelo de fatura Litware**.
5. Selecione **Criar configuração**.
6. [Marque](er-quick-start2-customize-report.md#MarkFormatRunnable) a versão de [rascunho](general-electronic-reporting.md#component-versioning) do mapeamento derivado como disponível para uso no runtime:

    1. No Painel de Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros do usuário**.
    2. Na caixa de diálogo **Parâmetros de usuário**, defina a opção **Executar configurações** como **Sim** e selecione **OK**.
    3. Selecione **Editar** para tornar a página editável, conforme necessário.
    4. Para a configuração **Mapeamento de modelo de fatura Litware** selecionada na árvore de configuração, defina a opção **Executar rascunho** como **Sim**.

7. No Painel de Ação, selecione **Designer** para revisar os mapeamentos de modelo dessa configuração.

    ![Analisar os mapeamentos de modelo de fatura de projeto na página Mapeamento de modelo para fonte de dados.](./media/er-multiple-model-mappings-image5.png)

    > [!TIP]
    > Agora, você pode abrir qualquer um dos componentes de mapeamento do modelo de ER da configuração de ER no designer para configurar a lógica personalizada. Para obter mais informações, consulte [Personalizar a configuração de mapeamento de modelo](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration).

8. Feche a página **Modelo para mapeamento de fonte de dados**.

Agora, você tem as configurações **Mapeamento de modelo de fatura** e **Mapeamento de modelo de fatura para Litware**, cada uma com um mapeamento de modelo configurado para a definição raiz **InvoiceCustomer**. Atribua explicitamente um dos mapeamentos de modelo como o mapeamento de modelo padrão usado por qualquer um dos formatos de ER, como o formato **Fatura de texto livre (Excel)** que contém uma fonte de dados de modelo que tem a definição raiz **InvoiceCustomer**. Caso contrário, quando você executar, editar ou validar um dos formatos de ER, a seguinte exceção será lançada para notificar que nenhum mapeamento de modelo padrão foi explicitamente atribuído:
 
> Existe mais de um mapeamento de modelo para o "\<model name\> (\<root descriptor\>)" modelo de dados nas configurações \<configuration names separated by commas\>. Defina uma das configurações como padrão.

![Abrir o formato para edição na página Configurações.](./media/er-multiple-model-mappings-image6.gif)

### <a name="customize-the-project-invoice-model-mapping-rdp-configuration"></a>Personalizar a configuração do mapeamento de modelo de fatura (RDP)

1. Na página **Configurações**, na árvore de configuração no painel esquerdo, selecione **Mapeamento de modelo de fatura de projeto (RDP)**.
2. No Painel de Ações, selecione **Criar configuração**.
3. Na caixa de diálogo **Criar configuração**, no campo **Novo**, selecione **Derivar do Nome: mapeamento de modelo de fatura de projeto (RDP), Microsoft**.
4. No campo **Nome**, insira **Mapeamento de modelo de fatura de projeto Litware**.
5. Selecione **Criar configuração**.
6. Para a configuração **Mapeamento de modelo de fatura de projeto Litware** selecionada na árvore de configuração, defina a opção **Executar rascunho** como **Sim**.
7. No Painel de Ação, selecione **Designer** para revisar os mapeamentos de modelo dessa configuração.

    ![Analisar os mapeamentos de modelo de fatura de projeto personalizado na página Mapeamento de modelo para fonte de dados.](./media/er-multiple-model-mappings-image7.png)

8. Feche a página **Modelo para mapeamento de fonte de dados**.

Agora, temos as configurações **Mapeamento de modelo de fatura**, **Mapeamento de modelos de nota fiscal de projeto (RDP)** e **Mapeamento de modelo de fatura de projeto Litware**. Cada uma dessas configurações tem um mapeamento de modelo configurado para a definição raiz **InvoiceProject**. Atribua explicitamente um dos mapeamentos de modelo como o mapeamento de modelo padrão usado por qualquer um dos formatos de ER. Por exemplo, use o formato **Fatura de projeto (Excel)** que contém uma fonte de dados de modelo que tem a definição raiz **InvoiceProject**. Caso contrário, quando você executar ou editar um dos formatos de ER, uma exceção será lançada para notificar que nenhum mapeamento de modelo padrão foi explicitamente atribuído.

## <a name="select-the-derived-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Selecione a configuração derivada Mapeamento de modelo de fatura Litware como a configuração que contém mapeamentos de modelo padrão

1. Na página **Configurações**, na árvore de configuração no painel esquerdo, selecione **Mapeamento de modelo de fatura Litware**.
2. Defina a opção **Padrão do mapeamento de modelo** como **Sim**.

    ![Configurar o mapeamento do modelo como o mapeamento de modelo padrão na página Configurações.](./media/er-multiple-model-mappings-image8.png)

    Por causa dessa configuração, o mapeamento de modelo **Cópia da fatura de cliente** é usado quando você executa a **Fatura de texto livre (Excel)** ou quando você a edita ou valida. O mapeamento de modelo **Fatura de cliente** da configuração **Mapeamento de modelo de fatura** é ignorada.

    Agora você pode abrir o formato **Fatura de texto livre (Excel)** para analisar no Designer de formato.

## <a name="select-the-derived-project-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Selecione a configuração derivada Mapeamento de modelo de fatura de projeto Litware como a configuração que contém mapeamentos de modelo padrão

1. Na página **Configurações**, na árvore de configuração no painel esquerdo, selecione **Mapeamento de modelo de fatura de projeto Litware**.
2. Defina a opção **Padrão do mapeamento de modelo** como **Sim**.

    Nesse caso, diferentemente do caso descrito para a configuração de **Mapeamento de modelo de fatura Litware** na seção anterior, não é possível iniciar o uso do mapeamento de modelo **Cópia de InvoiceProject** da configuração **Mapeamento de modelo de fatura Litware**. Duas configurações que contêm um mapeamento de modelo para a definição raiz **InvoiceProject** estão marcadas como a configuração padrão no momento. Portanto, elas têm a mesma prioridade de uso. Para resolver esse problema, conclua as etapas restantes deste procedimento.

3. Na árvore de configuração no painel esquerdo, selecione **Mapeamento de modelo de fatura Litware**.
4. No Painel de Ação, selecione **Designer**.
5. Na página **Mapeamento de modelo para fonte de dados**, selecione **Editar** para tornar a página editável, conforme necessário.
6. Selecione o mapeamento de modelo **Cópia da fatura de projeto** e marque a caixa de seleção **É excluído** para ele.

    ![Configurar o mapeamento do modelo como excluído virtualmente na página Mapeamento de modelo para fonte de dados.](./media/er-multiple-model-mappings-image9.png)

    Por causa dessa configuração, a configuração **Mapeamento de modelo de fatura Litware** é tratada como se não tivesse nenhum mapeamento de modelo para a definição raiz **InvoiceProject**. O mapeamento de modelo **Cópia de InvoiceProject** é emitido por padrão. A configuração **Mapeamento de modelo de fatura de projeto Litware**, que contém este mapeamento de modelo, é marcada como a configuração padrão. Como ela está marcada como padrão, ela tem uma prioridade maior do que o mapeamento de modelo **InvoiceProject** da configuração **Mapeamento de modelo de fatura de projeto (RDP)**.

## <a name="other-considerations"></a>Outras considerações

O mapeamento de modelo **Cópia de InvoiceProject** da configuração **Mapeamento de modelo de fatura de projeto Litware** foi criado para usar a fonte de dados **ReportDataProvider**. A fonte de dados faz parte do tipo de *Objeto* que se refere à classe de aplicativo **PsaProjInvoiceDP**. Essa classe é implementada como o provedor de dados do relatório do SQL Server Reporting Services (SSRS) da fatura de projeto da estrutura de gerenciamento de impressão. Selecione esta fonte de dados como o [ponto de integração de ER](er-apis-app10-0-11.md#api-to-run-a-format-mapping-for-the-generation-of-outbound-documents). A implementação atual de ER para relatórios de gerenciamento de impressão leva essa configuração em conta. Para obter mais detalhes, revise o código-fonte da classe de aplicativo **ERPrintMgmtDataProviderReport**. No tempo de execução, a atribuição da fonte de dados **ReportDataProvider** como ponto de integração de mapeamento de modelo força o Finance a tratar esse componente de mapeamento com uma prioridade maior do que o componente de mapeamento **InvoiceProject** da configuração **Mapeamento de modelo de fatura de projeto (RDP)**.

## <a name="see-also"></a>Consulte também

- [Gerenciar o mapeamento do modelo ER em configurações ER separadas](./tasks/er-manage-model-mapping-configurations-july-2017.md)
- [Configurar mapeamentos do modelo ER dependente do contexto do país/região](er-country-dependent-model-mapping.md)
- [Alteração na API da estrutura de Relatório eletrônico](er-apis-app10-0-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]