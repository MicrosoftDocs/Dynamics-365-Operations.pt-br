---
title: Criar uma nova solução ER para imprimir etiquetas ZPL
description: Este tópico explica como criar uma nova solução de relatório eletrônico (ER) para imprimir etiquetas ZPL (Linguagem de Programação Zebra).
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 8e5fb1515d4bdf36c22f617b6bfd2fa3ce3efa36
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388582"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>Criar uma nova solução ER para imprimir etiquetas ZPL

[!include [banner](../includes/banner.md)]

Este tópico explica como um usuário no administrador do sistema, no desenvolvedor de relatórios eletrônicos ou na função consultor funcional de relatórios eletrônicos pode configurar parâmetros da estrutura [Relatório Eletrônico (ER)](general-electronic-reporting.md), criar as [configurações](general-electronic-reporting.md#Configuration) de ER necessárias de uma nova solução ER para acessar os dados do sistema de gerenciamento de depósito e gerar etiquetas de localização de depósito personalizado no formato da Linguagem de Programação Zebra (ZPL) II. Essas etapas podem ser concluídas na empresa **USRT**.

## <a name="business-scenario"></a>Cenário de negócios

Você representa uma empresa que implementou o gerenciamento de depósito no Microsoft Dynamics 365 Finance. Cada local do depósito deve ser rotulado com uma etiqueta autocolante que inclui um código de barras. Os trabalhadores de depósito usarão leitores de código de barras para ler os códigos de barras.

Todos os locais de depósito foram rotulados no escopo de atividades de pré-ativação. No entanto, você também deve ser capaz de imprimir etiquetas de localização de depósito sob demanda, caso as etiquetas existentes sejam danificadas ou as prateleiras de depósito sejam reconfiguradas. Usando a funcionalidade ER recém-liberada, você pode configurar uma nova solução ER que permita a um supervisor de depósito imprimir etiquetas diretamente em uma impressora de etiquetas térmica.

## <a name="configure-the-er-framework"></a>Configurar a estrutura de ER

Siga as etapas em [Configurar a estrutura de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar o conjunto mínimo de parâmetros de ER. Você deve concluir essa configuração antes de começar a usar a estrutura de ER para criar uma nova solução ER.

## <a name="design-a-domain-specific-data-model"></a>Criar um modelo de dados de domínio específico

Criar uma nova configuração de ER que contenha um componente de [modelo de dados](er-overview-components.md#data-model-component) para o domínio de gerenciamento de depósito. Esse modelo de dados será usado como uma fonte de dados depois, quando você criar um formato ER para gerar etiquetas de localização de depósito.

### <a name="import-a-data-model-configuration"></a>Importar uma configuração de modelo de dados

Siga estas etapas para importar o modelo de dados necessário de um arquivo XML fornecido pela Microsoft. Como alternativa, você pode criar seu próprio modelo de dados, conforme descrito na próxima seção.

1. Baixe o arquivo [Warehouse model.version.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml) e salve-o no computador local.
2. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
4. Na página **Configurações**, no Painel de Ações, selecione **Trocar** \> **Carregar de arquivo XML**.
5. Selecione **Procurar** e, depois, localize e selecione o arquivo **Warehouse model.version.1.xml**.
6. Selecione **OK** para importar a configuração.

![Configuração do modelo de dados de ER importado na página Configurações.](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>Criar uma configuração de modelo de dados

Em vez de importar o arquivo de modelo de dados fornecido pela Microsoft, você pode criar um modelo de dados do zero. Para obter um exemplo que mostra como concluir essa tarefa, consulte [Criar uma nova configuração de modelo de dados](er-quick-start1-new-solution.md#DesignDataModel).

### <a name="review-the-data-model"></a>Revisar o modelo de dados

Você pode exibir uma versão editável do modelo de dados configurado na página **Designer de modelos de dados**.

![Estrutura do modelo de dados ER na página Designer de modelo de dados.](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>Criar um mapeamento de modelo para o modelo de dados configurado

Como usuário na função de Desenvolvedor de Relatório Eletrônico, você deve criar uma nova configuração de ER que contenha um componente de [mapeamento de modelos](er-overview-components.md#model-mapping-component) para o modelo de dados de Depósito. Esse componente implementa o modelo de dados configurado para o Dynamics 365 Finance e é específico desse aplicativo. Você deve configurá-lo para especificar os objetos de aplicativo que serão usados para preencher o modelo de dados configurado com os dados do aplicativo no tempo de execução. Para concluir essa tarefa, você deve compreender como a estrutura de dados do domínio comercial de gerenciamento de depósito é implementada no Finance.

### <a name="import-a-model-mapping-configuration"></a>Importar uma configuração de mapeamento de modelo

Siga estas etapas para importar o mapeamento de modelo necessário de um arquivo XML fornecido pela Microsoft. Como alternativa, você pode criar seu próprio mapeamento de modelo, conforme descrito na próxima seção.

1. Baixe o arquivo [Warehouse model mapping.version.1.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml) e salve-o no computador local.
2. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
4. Na página **Configurações**, no Painel de Ações, selecione **Trocar** \> **Carregar de arquivo XML**.
5. Selecione **Procurar** e, depois, localize e selecione o arquivo **Warehouse model mapping.version.1.1.xml**.
6. Selecione **OK** para importar a configuração.

![Configuração do mapeamento de modelo ER importado na página Configurações.](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>Crie uma configuração de mapeamento de modelo

Em vez de importar o arquivo de mapeamento de modelo fornecido pela Microsoft, você pode criar um mapeamento de modelo do zero. Para obter um exemplo que mostra como concluir essa tarefa, consulte [Criar uma nova configuração de mapeamento de modelo](er-quick-start1-new-solution.md#CreateModelMapping).

### <a name="review-the-model-mapping"></a>Revisar o mapeamento de modelos

Você pode exibir uma versão editável do mapeamento de modelo configurado na página **Designer de mapeamento de modelo**.

![Estrutura de mapeamento de modelo de ER na página Designer de mapeamento de modelo.](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>Criar um formato

Como usuário na função de consultor funcional de relatório eletrônico, você deve criar uma nova configuração do ER contendo um componente de [formato](er-overview-components.md#format-component). Para configurar este componente, você usará o código do ZPL II para especificar o layout da etiqueta de localização do depósito.

### <a name="import-a-format-configuration"></a>Importar uma configuração de formato

Siga estas etapas para importar o formato exigido de um arquivo XML fornecido pela Microsoft. Como alternativa, você pode criar seu próprio formato, conforme descrito na próxima seção.

1. Baixe o arquivo [Warehouse location labels.version.1.1.xml](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml) e salve-o no computador local.
2. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
4. Na página **Configurações**, no Painel de Ações, selecione **Trocar** \> **Carregar de arquivo XML**.
5. Selecione **Procurar** e, depois, localize e selecione o arquivo **Warehouse location labels.version.1.1.xml**.
6. Selecione **OK** para importar a configuração.

![Configuração do formato de ER importado na página Configurações.](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>Criar uma configuração de formato

Em vez de importar o arquivo de formato fornecido pela Microsoft, você pode criar um formato do zero. Para obter um exemplo que mostra como concluir essa tarefa, consulte [Criar uma nova configuração de formato](er-quick-start1-new-solution.md#FormatCreate).

### <a name="review-the-format"></a>Revisar o formato

Você pode exibir uma versão editável do formato configurado na página **Designer de formato**.

![Estrutura do formato de ER na página Designer de formato.](./media/er-design-zpl-labels-format.png)

A fonte de dados `model.Location.Label` deste formato é configurada para gerar etiquetas contendo as seguintes informações:

- O título do depósito como texto
- O título do depósito como um código de barras
- O título do local
- Dígitos de verificação

Na página **Designer de fórmulas** para a fonte de dados, a fórmula do ER usada para gerar etiquetas inclui uma função `CONCATENATE` que combina as informações no layout desejado.

![Fórmula para a fonte de dados na página Designer de fórmulas.](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> O layout da etiqueta foi projetado para que o título do local e os dígitos de verificação sejam alinhados no centro da etiqueta. No entanto, o ZPL II não oferece suporte ao alinhamento centralizado de códigos de barras. Portanto, a fórmula da fonte de dados `model.Location.Warehouse.Alignment` é usada para alinhar o código de barras no centro da etiqueta. Essa fórmula calcula o deslocamento à esquerda do código de barras, com base no número de caracteres no título do depósito.

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>Preparar seu ambiente para a visualização de etiquetas geradas

O exemplo a seguir usa um aplicativo de emulador de impressora para etiquetas de ZPL para mostrar uma visualização das etiquetas geradas na tela. Siga estas etapas para habilitar esta opção.

1. Adicione o destino de ER de [impressora](er-destination-type-print.md) para o formato de ER **etiqueta de localização do depósito** e configure-o para enviar etiquetas geradas do Finance ao [Agente de Roteamento de Documentos (DRA)](install-document-routing-agent.md).
2. Instale e configure o DRA para rotear etiquetas geradas do Finance para uma impressora local acessível da estação de trabalho atual.
3. Adicione uma impressora local para a estação de trabalho atual e configure-a para passar etiquetas geradas do DRA para um aplicativo de emulador de impressora.
4. Instale um aplicativo emulador de impressora como uma extensão do navegador da Web Chrome e configure-o para passar etiquetas geradas de uma impressora local para um serviço Web que processará etiquetas geradas e as devolverá ao emulador de impressora para visualização.

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>Relatório de ER</p>
<p>Destino da impressora</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>Agente de roteamento de documentos</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>Impressora local</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>Emulador de impressora</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>Renderização de serviço Web</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>Instalar e configurar um aplicativo de emulador de impressora

Adicione um aplicativo de emulador de impressora para o mecanismo de renderização do ZPL no navegador da Web Chrome. Este exemplo usa o emulador de [impressora ZPL](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo) baseado no [serviço Web Labelary ZPL](http://labelary.com/service.html). O aplicativo de emulador de impressora passará etiquetas geradas no formato ZPL de uma impressora local para o serviço Web e, depois, retornará etiquetas como arquivos PDF ou PNG para visualização.

1. Na loja da Web do Chrome, localize e selecione o aplicativo de emulador de impressora a ser usado. Selecione **Adicionar ao Chrome** para adicioná-lo ao navegador da Web do Chrome.

    ![Adicionando o aplicativo de emulador de impressora ao navegador da Web do Chrome a partir da loja da Web do Chrome.](./media/er-design-zpl-labels-add-app.png)

2. Selecione **Iniciar aplicativo** para executar o aplicativo de emulador de impressora a partir do navegador da Web do Chrome.

    ![Executando o aplicativo de emulador de impressora a partir do navegador da Web do Chrome.](./media/er-design-zpl-labels-run-app.png)

3. Configure o aplicativo em execução:

    1. Desative o aplicativo.
    2. Nas configurações da impressora, defina o host como **127.0.0.1**.
    3. Defina a porta como **9100**.

        ![Configurando o aplicativo de emulador de impressora.](./media/er-design-zpl-labels-configure-app.png)

    4. Reative o aplicativo. Você deve receber uma mensagem indicando que a impressora foi iniciada no host e na porta especificados.

        ![Aplicativo de emulador de impressora reativado.](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> Como o aplicativo de emulador de impressora usado neste exemplo depende de um serviço Web para processar etiquetas, certifique-se de que as suas configurações de segurança lhe permitam se comunicar com o serviço. Caso contrário, o aplicativo não receberá as etiquetas renderizadas e nenhuma visualização dessas etiquetas estará disponível.

### <a name="add-and-configure-a-local-printer"></a>Adicionar e configurar uma impressora local

[Adicione uma nova impressora local](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b) que possa ser usada pelo dispositivo atual para passar etiquetas geradas do DRA para o aplicativo de emulador de impressora.

1. No Windows, selecione **Iniciar** \> **Configurações** \> **Dispositivos** \> **Impressoras \& Scanners**.
2. Selecione **Impressoras \& Configurações de scanners**.
3. Para **Adicionar uma impressora ou um scanner**, selecione **Adicionar dispositivo**.
4. Para **A impressora que desejo não está listada**, selecione **Adicionar manualmente**.
5. No campo **Localizar uma impressora por outras opções**, selecione **Adicionar uma impressora local ou impressora de rede com configurações manuais**.
6. No campo **Escolha uma porta de impressora**, selecione **Criar uma nova porta** e siga estas etapas:

    1. No campo **Tipo de porta**, selecione **Porta TCP/IP padrão**.
    2. No campo **Nome do host ou endereço IP**, insira **127.0.0.1**.
    3. No campo **Nome da porta**, insira **ZPL**.
    4. Aguarde até que a operação **Detecção de porta TCP/IP** seja concluída.
    5. No campo **Tipo de dispositivo**, selecione **Personalizado** e, depois, **Configurações**.
    6. Verifique se as seguintes configurações de porta foram especificadas:

        - **Nome da porta:** ZPL
        - **Nome da impressora ou endereço IP:** 127.0.0.1
        - **Protocolo:** matéria-prima
        - **Número da porta:** 9100

7. No campo **Instalar o driver de impressora**, selecione **Genérico/somente texto**.
8. No campo **Nome da impressora**, insira **ZebraPrinter**.

![Adicionar uma impressora local para o dispositivo atual.](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>Instalar e configurar o DRA

Prepare o DRA para passar etiquetas geradas do Finance para a impressora local configurada.

1. [Instalar o DRA](install-document-routing-agent.md#install-the-document-routing-agent).
2. [Configurar o DRA](install-document-routing-agent.md#configure-the-document-routing-agent).
3. [Registre a impressora local](install-document-routing-agent.md#register-network-printers) no DRA.
4. [Ative a impressora local](install-document-routing-agent.md#administer-network-printers) no seu ambiente do Finance.

![Preparar o DRA para imprimir etiquetas geradas.](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>Configurar o destino do ER

Prepare o destino de ER para passar etiquetas geradas do Finance para o DRA.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Destino de relatório eletrônico**.
2. Na página **Destino de relatório eletrônico** no Painel de Ações, selecione **Novo**.
3. No campo **Referência**, selecione **Etiquetas de localização do depósito**.
4. Na Guia Rápida **Destino do arquivo**, selecione **Novo**.
5. No campo **Nome**, insira **Etiquetas**.
6. No campo **Nome do componente de arquivo**, selecione **Relatório**.
7. Selecione **Configurações**.
8. Na caixa de diálogo **Configurações de destino** na guia **Impressora**, defina a opção **Habilitado** como **Sim**.
9. No campo **Nome da impressora**, selecione **ZebraPrinter**.
10. No campo **Tipo de roteamento de documento**, selecione **ZPL**.
11. Selecione **OK**.

![Configuração do destino de ER para o formato de Etiquetas de localização de depósito na página Destino de relatório eletrônico.](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>Analisar locais de depósito

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Depósito** \> **Localizações**.
2. Na página **Locais**, filtre para exibir somente locais com um valor no campo **Dígitos de verificação**.

![Revisão de localizações de depósito na página Locais.](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>Imprimir etiquetas de localização de depósito

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração, expanda **Modelo de depósito** e selecione **Etiquetas de localização de depósito**.
3. No Painel de Ação, selecione **Executar**.
4. Na caixa de diálogo **Parâmetros do relatório eletrônico**, na guia **Registros a serem incluídos**, selecione **Filtro**.
5. Na guia **Intervalo**, localize a linha em que o campo **Tabela** está definido como **Localizações** e o campo **Campo** está definido como **Localização**. No campo **Critérios**, insira **LPEnabled**.
6. Selecione **OK**.
7. Selecione **OK**. Uma etiqueta é gerada e mostrada na página de visualização no aplicativo de emulador de impressora.

![Revisão de uma etiqueta gerada na página de visualização do aplicativo de emulador de impressora Zpl.](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>Modificar o layout de uma etiqueta

Você pode alterar o layout atual de etiquetas de localização de depósito. O exemplo a seguir mostra como alterar o layout de forma que as etiquetas geradas incluam uma ID de perfil de local.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Defina **Usar destinos para status de rascunho** [Parâmetro de usuário ER](electronic-reporting-destinations.md#applicability) como **Sim**.
3. Na página **Configurações**, na árvore de configuração, expanda **Modelo de depósito** e selecione **Etiquetas de localização de depósito**.
4. Selecione **Designer**.
5. Na página **Designer de formato** , na guia **Mapeamento** , selecione a fonte de dados `model.Location.Label`.
6. Na caixa de diálogo **Propriedades da fonte de dados**, selecione **Editar** \> **Editar fórmula**.
7. Na página **Designer de fórmulas**, no campo **Fórmula**, revise a fórmula ER que é usada para gerar etiquetas.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. Atualize a fórmula para adicionar uma ID de perfil de local a etiquetas geradas.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. Selecione **Salvar**.
10. Selecione **OK**.
11. No Painel de Ação, selecione **Executar**.
12. Na caixa de diálogo **Parâmetros do relatório eletrônico**, na guia **Registros a serem incluídos**, selecione **Filtro**.
13. Na guia **Intervalo**, localize a linha em que o campo **Tabela** está definido como **Localizações** e o campo **Campo** está definido como **Localização**. No campo **Critérios**, insira **Bay**.
14. Selecione **OK**.
15. Selecione **OK**. Uma etiqueta é gerada e mostrada na página de visualização no aplicativo de emulador de impressora.

![Revisão de uma etiqueta gerada que inclua uma ID do perfil de localização na página de visualização do aplicativo de emulador de impressora ZPL.](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>Codificação

> [!NOTE]
> Você deve sincronizar a configuração de codificação do componente **Comum\\Arquivo** do formato ER editável e a configuração apropriada da etiqueta projetada. O valor do campo **[Codificação](er-suppress-bom-characters.md)** do componente **Comum\\Arquivo** não deve contradizer um comando ZPL usado para controlar a codificação da etiqueta (por exemplo, o comando `^CI`). O ER não valida se essas configurações estão sincronizadas.

## <a name="additional-resources"></a>Recursos adicionais

[Destino da impressora](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
