---
title: Importar e exportar cálculos de imposto
description: Este artigo fornece informações sobre a funcionalidade de importação e exportação do serviço de cálculo de imposto.
author: Kai-Cloud
ms.date: 10/17/2022
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
ms.openlocfilehash: 8666d4971e36279ebd2b1396de7cab37680980e6
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690224"
---
# <a name="import-and-export-tax-calculations"></a>Importar e exportar cálculos de imposto

Este artigo fornece informações sobre a funcionalidade de importação e exportação do serviço de cálculo de imposto. Essa funcionalidade ajuda a garantir uma experiência de configuração flexível e eficiente.

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

## <a name="import-feature-demo-data"></a>Importar dados de demonstração do recurso

Siga estas etapas para importar dados de demonstração do recurso.

1. Entre no [RCS](https://marketing.configure.global.dynamics.com/).
2. No espaço de trabalho **Recursos de globalização**, selecione **Recursos** e, em seguida, selecione o bloco **Cálculo de Imposto**.
3. Selecione **Importar** e, na página **Importar recurso do Repositório global**, selecione **Sincronizar**. 
4. Na tabela, selecione o recurso **imposto-cálculo-recurso-demonstração-dados** e, depois, selecione **Importar**.
5. Selecione **Exibir** para revisar os códigos de imposto, grupos e regras de aplicabilidade definidos no recurso importado.
6. No Finance, alterne para a entidade legal **DEMF** e, depois, acesse **Imposto** \> **Configuração** \> **Configuração do imposto** \> **Parâmetros de cálculo do imposto**.
7. Na guia **Geral**, selecione **Habilitar Serviço de Cálculo de Imposto**.
8. No campo **Nome de configuração do recurso**, selecione **imposto-cálculo-recurso-demonstração-dados**.
9. Selecione um **Período de liquidação** e um **Grupo de lançamento contábil** para os novos códigos de imposto de demonstração e, depois, selecione **Confirmar**.
10. Selecione **Salvar**.

> [!NOTE]
> O recurso de demonstração **imposto-cálculo-recurso-demonstração-dados** se baseia na versão **40.54.234** do recurso e se destina à entidade legal de demonstração **DEMF**. Verifique se o Finance e o RCS foram atualizados para a versão 10.0.26 ou posterior.
