---
title: Importar e exportar cálculos de imposto
description: Este tópico fornece informações sobre a funcionalidade de importação e exportação do serviço de cálculo de imposto.
author: Kai-Cloud
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-11-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 02ad47b5f350969b4935a8f383ddf26a7ce7a46a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690880"
---
# <a name="import-and-export-tax-calculations"></a>Importar e exportar cálculos de imposto

Este tópico fornece informações sobre a funcionalidade de importação e exportação do serviço de cálculo de imposto. Essa funcionalidade ajuda a garantir uma experiência de configuração flexível e eficiente.

## <a name="import-and-export-tax-codes"></a>Importar e exportar códigos de imposto

### <a name="export-templates"></a>Exportar modelos

1. Entre no [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/).
2. No espaço de trabalho **Recursos de globalização**, selecione **Recursos** e, em seguida, selecione o bloco **Cálculo de Imposto**.
3. Selecione um recurso existente ou [crie um recurso](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. Na grade **Versões**, selecione **Editar**.
5. Na página do recurso **Cálculo de imposto**, defina a [versão de configuração](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. Na guia **Códigos de imposto**, selecione **Importar**.
7. Selecione **Exportar um modelo de código de imposto** para baixar o arquivo **TaxCodesTemplate.zip**.
8. Descompacte **TaxCodesTemplate.zip**. Os modelos de código de imposto são compactados separadamente de acordo com o valor da **Origem do cálculo**.
9. Descompacte **Por valor líquido.zip** para obter os seguintes arquivos CSV (valores separados por vírgula):

    - **TaxCode.csv** – insira os códigos de imposto.
    - **TaxLimit.csv** – insira os limites de imposto para cada código de imposto.
    - **TaxRate.csv** – insira as taxas de imposto para cada código de imposto.

> [!NOTE]
> Por padrão, as entradas para o código de imposto de **Exemplo** estão disponíveis nos modelos. Se o código de imposto de **Exemplo** não for removido dos arquivos CSV, ele será importado para o recurso.

### <a name="import-tax-codes"></a>Importar códigos de imposto

Siga estas etapas para importar o código de imposto de **Exemplo** no modelo para o recurso de cálculo de imposto.

1. No RCS, na página do recurso **Cálculo de imposto**, na guia **Códigos de imposto**, selecione **Importar**.
2. Selecione **Procurar**, encontre e selecione o arquivo **TaxCode.csv** e, no campo **Tabela de destino**, selecione o **Código de imposto**.
3. Selecione **OK** para importar o código de imposto.
4. Encontre e selecione o arquivo **TaxRate.csv** e, no campo **Tabela de destino**, selecione **Taxa de imposto**.
5. Selecione **OK** para importar a taxa de imposto.
6. Encontre e selecione o arquivo **TaxLimit.csv** e, no campo **Tabela de destino**, selecione **Limite de imposto**.
7. Selecione **OK** para importar o limite de imposto.

Você também pode importar diretamente o arquivo zip que inclui todos os três arquivos CSV. Dessa forma, é possível concluir a importação com rapidez e facilidade.

1. No RCS, na página do recurso **Cálculo de imposto**, na guia **Códigos de imposto**, selecione **Importar**.
2. Selecione **Procurar**, encontre e selecione o arquivo **Por valor líquido.zip** e, em seguida, selecione **OK**.

### <a name="export-tax-codes"></a>Exportar códigos de imposto

1. No RCS, na página do recurso **Cálculo de imposto**, na guia **Códigos de imposto**, selecione **Exportar**.

    O botão **Exportar** ficará disponível quando houver, pelo menos, um código de imposto na grade **Códigos de imposto**.

2. Selecione **OK** para exportar todos os códigos de imposto do recurso em um arquivo zip.

> [!NOTE]
> Use o arquivo exportado como um modelo para importar códigos de imposto para o recurso correspondente.

## <a name="import-and-export-applicability-rules"></a>Importar e exportar regras de aplicabilidade

### <a name="export-applicability-rules"></a>Exportar regras de aplicabilidade

1. Entre no [RCS](https://marketing.configure.global.dynamics.com/).
2. No espaço de trabalho **Recursos de globalização**, selecione **Recursos** e, em seguida, selecione o bloco **Cálculo de Imposto**.
3. Selecione um recurso existente ou [crie um recurso](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. Na grade **Versões**, selecione **Editar**.
5. Na página do recurso **Cálculo de imposto**, defina a [versão de configuração](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. Na guia **Aplicabilidade do grupo de impostos**, selecione as linhas na grade **Configurar aplicabilidade do grupo de impostos**.
7. Selecione o botão **Abrir no Microsoft Office** e, em seguida, selecione **Matriz de aplicabilidade dinâmica do serviço de imposto**.

    [![Exportando regras de aplicabilidade para o Microsoft Excel na página do recurso Cálculo de imposto.](./media/tax-cal-import-export-1.png)](./media/tax-cal-import-export-1.png)

8. Selecione **Baixar** para exportar as linhas selecionadas para uma planilha do Microsoft Excel.

### <a name="import-applicability-rules"></a>Importar regras de aplicabilidade

A planilha do Excel que você baixou contém a estrutura da grade **Configurar aplicabilidade do grupo de impostos**. Você pode adicionar novas regras diretamente na planilha. Quando terminar, siga estas etapas para importar as novas regras novamente para a grade **Configurar aplicabilidade do grupo de impostos**.

1. Na planilha do Excel, selecione e copie as linhas a serem importadas.
2. No RCS, na página do recurso **Cálculo de imposto**, na guia **Aplicabilidade do grupo de impostos**, selecione **Adicionar** para inserir um registro vazio na parte inferior da grade **Configurar aplicabilidade do grupo de impostos**.
3. Selecione **Ctrl + V** para colar as linhas copiadas na grade.
4. Selecione **Salvar**.
