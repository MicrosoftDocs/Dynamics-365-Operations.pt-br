---
title: Declaração de IVA (Dinamarca)
description: Este artigo descreve como configurar e gerar uma declaração de IVA (imposto sobre valor agregado) antecipada para a Dinamarca.
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 99c8b7a35258116adfe7433e884564d64dbf140f
ms.sourcegitcommit: 3aa3dedc3123cb079614762e2718841c2f7d7d35
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "9812123"
---
# <a name="vat-declaration-denmark"></a>Declaração de IVA (Dinamarca)

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar a declaração de IVA (imposto sobre valor agregado) para a Dinamarca e visualizá-la no Microsoft Excel.

Para gerar automaticamente o relatório, crie primeiramente códigos de impostos suficientes para manter uma contabilização de IVA separada para cada caixa na declaração de IVA antecipada. Além disso, nos parâmetros específicos do aplicativo do formato de relatório eletrônico (ER) para a declaração de IVA antecipada, associe os códigos de imposto com o resultado da pesquisa para as caixas na declaração de IVA.

Para a Dinamarca, você deve configurar a **Pesquisa de campos de relatório**. Para obter mais informações sobre como configurar parâmetros específicos do aplicativo, consulte a seção [Configurar parâmetros específicos do aplicativo para campos de declaração de IVA](#set-up-application-specific-parameters) mais adiante neste artigo.

Na tabela a seguir, a coluna "Resultado da pesquisa" mostra o resultado da pesquisa pré-configurado para uma linha de declaração de IVA específica no formato da declaração de IVA. Use essas informações para associar corretamente os códigos de imposto ao resultado da pesquisa e com a linha da declaração de IVA.

### <a name="vat-declaration-overview"></a>Visão geral da declaração de IVA

A declaração de IVA na Dinamarca contém as informações a seguir.

**VAT a pagar**

| Descrição                                                  | Base de impostos/Valor do imposto | Resultado da pesquisa/Total                                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IVA de saída                                                   | Valor de imposto          | **OutputVAT**</br> **DomesticVATUseTax** (também informado na caixa "IVA de entrada")                                                                                                                                                                                                                                                                       |
| IVA sobre mercadorias, etc. compradas no exterior                           | Valor de imposto          | **PurchaseGoodsAbroad**</br>**PurchaseGoodsAbroadUseTax** (também informado na caixa "IVA de entrada")</br>**PurchaseGoodsEU** (a base de impostos é informada na "Caixa A – aquisição de bens".)</br>**PurchaseGoodsEUUseTax** (O valor do imposto também informado na caixa "IVA de entrada". A base de impostos é informada na "Caixa A – aquisição de bens".)                   |
| IVA sobre serviços comprados no exterior sujeito a encargos revertidos | Valor de imposto          | **PurchaseServicesAbroad**</br> **PurchaseServicesAbroadUseTax** (também informado na caixa "IVA de entrada")</br>**PurchaseServicesEU** (A base de impostos é informada na "Caixa A – aquisição de serviços".)</br>**PurchaseServicesEUUseTax** (O valor do imposto também informado na caixa "IVA de entrada". A base de impostos é informada na "Caixa A – aquisição de serviços".) |
| Total a pagar                                                | Valor de imposto          | Total das três caixas anteriores                                                                                                                                                                                                                                                                                                            |

**Deduções**

| Descrição                                                                               | Base de impostos/Valor do imposto | Resultado da pesquisa/Total                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IVA de entrada                                                                                 | Valor de imposto          | **InputVAT**</br> **DomesticVATUseTax** (também informado na caixa "IVA de saída")</br>**PurchaseGoodsAbroadUseTax** (também informado na caixa "IVA sobre mercadorias, etc. compradas no exterior")</br>**PurchaseServicesAbroadUseTax** (também informado na caixa "IVA sobre serviços comprados no exterior, sujeito a um encargo revertido")</br>**PurchaseGoodsEUUseTax** (também informado na caixa "IVA sobre mercadorias, etc. compradas no exterior")</br> **PurchaseServicesEUUseTax** (também informado na caixa "IVA sobre serviços comprados no exterior, sujeito a um encargo revertido") |
| Direitos de óleo e de gás engarrafados                                                                  | Valor de imposto          | **OilGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Taxa de energia/eletricidade                                                                    | Valor de imposto          | **PowerElectricityDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Direitos de gás natural de gás de cidade                                                             | Valor de imposto          | **NaturalTownGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Direitos de carbono                                                                               | Valor de imposto          | **CarbonDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CO2Duty                                                                                   | Valor de imposto          | **CO2Duty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Encargo de água                                                                              | Valor de imposto          | **WaterCharge**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Total de deduções                                                                          | Valor de imposto          | Total das seis caixas anteriores                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Valor total de impostos (valor positivo = fazer pagamento, valor negativo = receber reembolso) | Valor de imposto          | "Total a pagar" – "Total de deduções"                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

**Informações suplementares**

| Descrição                                                                                                                                                                                                                                | Base de impostos/Valor do imposto | Resultado da pesquisa/Total                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|-------------------------------------------------|
| Caixa A – aquisição de mercadorias. O valor sem IVA de aquisição de mercadorias dentro da União.                                                                                                                                                   | Base de imposto            | **PurchaseGoodsEU PurchaseGoodsEUUseTax**       |
| Caixa A – aquisição de serviços. O valor sem IVA de aquisição de serviços dentro da União.                                                                                                                                             | Base de imposto            | **PurchaseServicesEU PurchaseServicesEUUseTax** |
| Caixa B – fornecimento de mercadorias – a ser informado em "vendas da UE sem IVA"/DK VIES. O valor sem IVA de fornecimento de mercadorias dentro da União                                                                                                           | Base de imposto            | **SalesGoodsEU**                                |
| Caixa B – fornecimentos – não deverá ser informado em "vendas da UE sem IVA"/DK VIES. O valor sem IVA de determinados suprimentos dentro da União, por exemplo: instalação, montagem, vendas à distância e novos meios de transporte para pessoas não tributáveis. | Base de imposto            | **SalesInstallationAssemblyEtcEU**              |
| Caixa B – fornecimento de serviços. O valor sem IVA do fornecimento de serviços dentro da União para o qual o comprador é responsável por pagar o IVA como encargo revertido – também deve ser informado em "vendas da UE sem IVA"/DK VIES.                          | Base de imposto            | **SalesServicesEU**                             |
| Caixa C – outros suprimentos. Valor do fornecimento de outras mercadorias e serviços que são fornecidos sem IVA no território da Dinamarca, a outros países membros da UE e a outras regiões ou outros territórios.                                     | Base de imposto            | **OtherSuppliesWithoutVAT**                     |

#### <a name="purchase-reverse-charge-vat"></a>IVA de encargos revertidos de compra

Se você configurar códigos de imposto para lançar o IVA de encargos revertidos de entrada usando o imposto sobre o uso, associe os códigos de imposto ao resultado da **Pesquisa de campos de Relatório** que contém "UseTax" no nome.

Como alternativa, você pode configurar dois códigos de impostos separados: um para IVA devido e um para dedução de IVA. Em seguida, associe cada código aos resultados de pesquisa correspondentes da **Pesquisa de campos de Relatório**.

Por exemplo, para aquisições tributáveis dentro da comunidade, configure o código do imposto **UT_S_EU** com imposto sobre o uso e associe-o ao resultado da pesquisa **PurchaseGoodsEUUseTax** de **Pesquisa de campos de Relatório**. Nesse caso, os valores de imposto que usam o código do imposto **UT_S_EU** são refletidos nas caixas "IVA sobre mercadorias, etc. compradas no exterior" e "IVA de entrada". As base de imposto são refletidas na "Caixa A – aquisição de mercadorias".

Como opção, configure dois códigos de impostos:

- **VAT_S_EU**, que tem um valor de taxa de imposto de -25%
- **InVAT_S_EU**, que tem um valor de taxa de imposto de -25%

Associe os códigos aos resultados de pesquisa da **Pesquisa de campos de relatório** da seguinte forma:

- Associe **VAT_S_EU** ao resultado da pesquisa **PurchaseGoodsEU**.
- Associe **InVAT_S_EU** ao resultado da pesquisa **InputVAT**.

Nesse caso, os valores que usam o código de imposto **VAT_S_EU** são refletidos nas caixas "IVA sobre mercadorias, etc. compradas no exterior "e "Caixa A – aquisição de mercadorias". Valores que usam o código do imposto **InVAT_S_EU** são refletidos na caixa "IVA de entrada".

Para obter mais informações sobre como configurar IVA de encargos revertidos, consulte [Encargos revertidos](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configurar parâmetros do sistema

Para gerar uma declaração de IVA, você deve configurar o número do IVA.

1. Acesse **Administração da organização** > **Organizações** > **Entidades legais**.
2. Selecione a entidade legal e **IDs de Registro**.
3. Selecione ou crie o endereço na Dinamarca e, em seguida, na Guia Rápida **ID do registro**, selecione **Adicionar**.
4. No campo **Tipo de registro**, selecione o tipo de registro dedicado à Dinamarca e que usa a categoria de registro **ID do IVA**.
5. No campo **Número de registro**, informe o número do imposto.
6. Na guia **Geral**, no campo **Efetivo**, insira a data em que o número entra em vigor.

Para obter mais informações sobre como configurar categorias de registro e tipos de registro, consulte [IDs de Registro](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-preview-for-denmark"></a>Configurar uma visualização da declaração de IVA para a Dinamarca

### <a name="import-er-configurations"></a>Importar configurações ER

Abra o espaço de trabalho **Relatório Eletrônico** e importe o formato de ER da **Declaração de IVA no Excel (DK)**.

Para obter mais informações, consulte [Baixar configurações ER do repositório global de serviço de configuração](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters"></a>Configurar parâmetros específicos do aplicativo para campos de declaração de IVA

> [!NOTE]
> Recomendamos habilitar o recurso **Usar parâmetros específicos do aplicativo das versões anteriores de formatos ER** no espaço de trabalho **Gerenciamento de recursos**. Quando o recurso está habilitado, os parâmetros configurados para a versão anterior de um formato ER se tornarão aplicáveis automaticamente à versão posterior do mesmo formato. Se o recurso não estiver habilitado, você deverá configurar explicitamente parâmetros específicos do aplicativo para cada versão de formato. O recurso **Usar parâmetros específicos do aplicativo das versões anteriores de formatos ER** está disponível no espaço de trabalho **Gerenciamento de recursos** a partir da versão 10.0.23 do Finance. Para obter mais informações sobre como configurar os parâmetros de um formato ER para cada entidade legal, consulte [Configurar os parâmetros de um formato ER de acordo com a entidade legal](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Para gerar automaticamente uma declaração de IVA, associe os códigos de imposto no aplicativo e os resultados da pesquisa na configuração ER.

Siga estas etapas para definir quais códigos de impostos geram quais caixas na declaração de IVA.

1. Vá para **Espaços de Trabalho** > **Relatório eletrônico** e selecione **Configurações de relatórios**.
2. Selecione a configuração **Declaração de IVA no Excel (DK)** e, em seguida, selecione **Configurações \> Configuração de parâmetros específicos do aplicativo**.
3. Na página **Parâmetros específicos do aplicativo**, na FastTab **Pesquisas**, selecione **Pesquisa de campos de relatório**.
4. Na FastTab **Condições**, defina os campos a seguir para associar os códigos de imposto e os campos de relatório.

    | Campo                  | Descrição                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Resultado da pesquisa          | Selecione o valor do campo do relatório. Para obter mais informações sobre os valores e suas atribuições às linhas da declaração de IVA, consulte a seção [visão geral da declaração de IVA](#vat-declaration-overview) anteriormente contida neste artigo.                                                                                               |
    | Código do imposto               | Selecione o código do imposto a ser associado ao campo do relatório. As transações de imposto lançadas que usam o código de imposto selecionado serão coletadas na caixa de declaração apropriada. Recomendamos que você separe os códigos de impostos de tal forma que um código de imposto gera valores em apenas uma caixa de declaração. |
    | Classificador de transação | Se você criou códigos de impostos suficientes para determinar uma caixa de declaração, selecione **\*Não em branco\***. Se você não criou códigos de imposto suficientes para que um código de imposto gere valores em apenas uma caixa de declaração, você pode configurar um classificador de transação. Os seguintes classificadores de transação a seguir estão disponíveis:</br>-   **Compra**</br>-   **PurchaseExempt** (compra isenta de impostos)</br>-   **PurchaseReverseCharge** (imposto a receber de um encargo revertido de compra)</br>-   **Vendas**</br>-   **SalesExempt** (venda isenta de impostos)</br>-   **SalesReverseCharge** (imposto sobre o encargo revertido de compra ou um encargo revertido de venda)</br>-   **Imposto sobre o uso**. </br>Para cada classificador de transação, também está disponível um classificador para a nota de crédito. Por exemplo, um desses classificadores é **PurchaseCreditNote** (nota de crédito de compra).</br>Certifique-se de criar duas linhas para cada código de imposto: um que tenha o valor do classificador da transação e um que tenha o classificador da transação para o valor da nota de crédito. |


    > [!NOTE]
    > Associe todos os códigos de imposto a resultados de pesquisa. Se nenhum código de imposto não gerar valores na declaração de IVA, associe-os ao **Outro** resultado de pesquisa.

    ![Página de parâmetros específicos do aplicativo.](media/7db74920fad66a0db7fad60758698cc0.png)


5. No campo **Estado**, altere o valor para **Concluído**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Configurar o formato de relatório de IVA para valores de visualização no Excel

1. No espaço de trabalho **Gerenciamento de recursos**, encontre e selecione o recurso **Relatórios de formato de declaração de IVA**. na lista e selecione **Habilitar agora**.
2. Vá para **Contabilidade** > **Configuração** > **Parâmetros de contabilidade**.
3. Na guia **Imposto**, na Guia Rápida **Opções de imposto**, no campo **Mapeamento de formatos da declaração de IVA**, selecione o formato de ER **Declaração de IVA no Excel (DK)**.

   Esse formato é impresso quando você executa o relatório **Imposto para o período de liquidação**. Também é impresso quando você seleciona **Imprimir** na página **Pagamentos de impostos**.

4. Na página **Autoridades de imposto**, selecione a autoridade de imposto e, no campo **Layout do relatório**, selecione **Padrão**.

Se você estiver configurando a declaração de IVA em uma entidade legal que tenha [vários registros de IVA](emea-reporting-for-multiple-vat-registrations.md), siga estas etapas:

1. Acesse **Contabilidade** \> **Configuração** \> **Parâmetros da contabilidade**.
2. Na guia **Imposto**, na Guia Rápida **Relatório eletrônico para países/regiões**, na linha de **DNK**, selecione o formato de ER **Declaração de IVA no Excel (DK)**.

## <a name="set-up-electronic-messages"></a>Configurar mensagens eletrônicas

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Baixar e importar o pacote de dados que contém exemplos de configurações para mensagens eletrônicas

O pacote de dados contém configurações de mensagens eletrônicas usadas para visualizar a declaração de IVA no Excel. Você pode estender essas configurações ou criar suas próprias. Para obter mais informações sobre como trabalhar com mensagens eletrônicas e criar suas próprias configurações, consulte [Mensagens eletrônicas](../general-ledger/electronic-messaging.md).

1. No [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2), na Biblioteca de ativos compartilhado, selecione **Pacote de dados** como o tipo de ativo e baixe o **Pacote de declaração de IVA DK**. O nome do arquivo baixado é **Pacote de declaração de IVA DK.zip**.
2. No Finance, no espaço de trabalho **Gerenciamento de dados**, selecione **Importar**.
3. Na FastTab **Importar**, no campo **Nome do grupo**, digite um nome para o trabalho.
4. Na guia rápida **Entidades selecionadas**, selecione **Adicionar arquivo**.
5. Na caixa de diálogo **Adicionar arquivo**, verifique se o campo **Formato de dados de origem** está definido como **Pacote**, selecione **Carregar e adicionar** e selecione o arquivo zip baixado anteriormente.
6. Selecione **Fechar**.
7. Depois que as entidades de dados forem carregadas, no painel de ação, selecione **importar**.
8. Acesse **Imposto** > **Consultas e relatórios** > **Mensagens eletrônicas** > **Mensagens eletrônicas** e valide o processamento da mensagem eletrônica que você importou (**Declaração de IVA DK**).

### <a name="configure-electronic-messages"></a>Configurar mensagens eletrônicas

1. Vá até **Imposto** > **Configuração** > **Mensagens eletrônicas** > **Ações de preencher registros**.
2. Selecione a linha para **DK Preencher registros de restituição de IVA** e selecione **Editar consulta**.
3. Use o filtro para especificar os períodos de liquidação a serem incluídos no relatório.
4. Se você deve relatar transações de imposto de outros períodos de liquidação em uma declaração diferente, crie uma nova ação **Preencher registros** e selecione os períodos de liquidação apropriados.

## <a name="preview-the-vat-declaration-in-excel"></a>Visualizar a declaração de IVA no Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a><a name="preview-vat-excel"></a>Visualizar a declaração de IVA no Excel a partir do Relatório de imposto para a tarefa periódica do período de liquidação

1. Vá até **Imposto** > **Tarefas periódicas** > **Declarações** > **Impostos** > **Relatar imposto do período de liquidação**.
2. No campo de **Período de liquidação**, selecione um valor.
3. No campo **Versão de liquidação do imposto**, selecione um dos valores a seguir:

    - **Original**: gera um relatório para as transações de impostos do pagamento do imposto original ou antes que o pagamento do imposto seja gerado.
    - **Correções**: gera um relatório para as transações de imposto de todos os pagamentos de imposto subsequentes para o período.
    - **Lista total**: gera um relatório para todas as transações de imposto do período, incluindo o original e todas as correções.

4. No campo **Data inicial**, selecione a data de início do período do relatório.
5. Selecione **OK** e analise o relatório do Excel.

### <a name="settle-and-post-sales-tax"></a>Liquidar e lançar imposto

1. Acesse **Imposto** > **Tarefas periódicas** > **Declarações** > **Impostos** > **Liquidar e lançar imposto**.
2. No campo de **Período de liquidação**, selecione um valor.
3. No campo **Versão de liquidação do imposto**, selecione um dos valores a seguir:

    - **Original**: gera o pagamento do imposto original para o período de liquidação.
    - **Últimas correções**: gera um pagamento de imposto de correção após a criação do pagamento original do imposto para o período de liquidação.

4. No campo **Data inicial**, selecione a data de início do período do relatório.
5. Selecione **OK**.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Visualizar a declaração de IVA no Excel a partir de um pagamento de imposto

1. Vá para **Imposto** > **Consultas e relatórios** > **Consultas de impostos** > **Pagamentos de impostos** e selecione uma linha de pagamento de impostos.
2. Selecione **Imprimir relatório** e **OK**.
3. Revise o arquivo do Excel gerado para a linha de pagamento de imposto selecionada.

> [!NOTE]
> O relatório é gerado somente para a linha de pagamento de imposto selecionada. Se você tiver que gerar, por exemplo, uma declaração corretiva que contenha todas as correções para o período, ou uma declaração substitutiva que contenha os dados originais e todas as correções, use a tarefa periódica **Relatar imposto do período de liquidação**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Gerar uma declaração de IVA de mensagens eletrônicas

Ao usar mensagens eletrônicas para gerar o relatório, você pode coletar dados de impostos de várias entidades legais. Para obter mais informações, consulte a seção [Executar uma declaração de IVA para várias entidades legais](#run-vat-declaration) mais adiante neste artigo.

O procedimento a seguir aplica-se ao exemplo de processamento de mensagens eletrônicas que você importou anteriormente da Biblioteca de ativos compartilhados do LCS.

1. Acesse **Imposto \> Consultas e relatórios \> Mensagens eletrônicas \> Mensagens eletrônicas**.
2. No painel esquerdo, selecione **DK Declaração de IVA**.
3. Na FastTab **Mensagens**, selecione **Novo** e, em seguida, na caixa de diálogo **Executar processamento**, selecione **OK**.
4. Selecione a linha da mensagem que é criada, insira uma descrição e especifique as datas inicial e final da declaração.

   > [!NOTE]
   > As etapas 5 a 7 são opcionais.

5. Opcional: na FastTab **Mensagens**, selecione **Coletar dados** e, em seguida, selecione **OK**. Os pagamentos de impostos que foram gerados anteriormente são adicionados à mensagem. Para obter mais informações, consulte a seção [Liquidar e lançar imposto](#settle-and-post-sales-tax) anteriormente neste artigo. Se pular esta etapa, você ainda poderá gerar uma declaração de IVA usando o campo **Versão da declaração de imposto** na caixa de diálogo **Declaração**.
6. Opcional: na FastTab **Itens de mensagem**, revise os pagamentos de impostos que são transferidos para processamento. Por padrão, todos os pagamentos de impostos do período selecionado que não foram incluídos em outras mensagens do mesmo processamento são incluídos.
7. Opcional: selecione **Documento original** para revisar os pagamentos de impostos ou selecione **Excluir** para excluir pagamentos de impostos do processamento. Se pular esta etapa, você ainda poderá gerar uma declaração de IVA usando o campo **Versão da declaração de imposto** na caixa de diálogo **Declaração**.
8. Na FastTab **Mensagens**, selecione **Atualizar status**. Na caixa de diálogo **Atualizar status**, selecione **Pronto para gerar** e, em seguida, selecione **OK**. Verifique se o status da mensagem foi alterado para **Pronto para gerar**.
9. Selecione **Gerar relatório**. Para visualizar os valores da declaração de IVA, na caixa de diálogo **Executar processamento**, selecione **Visualizar relatório** e, em seguida, selecione **OK**.
10. Na caixa de diálogo **Parâmetros de relatório eletrônico**, defina os campos, conforme descrito na seção [Visualizar a declaração de IVA no Excel a partir do Relatório de imposto para a tarefa periódica do período de liquidação](#preview-vat-excel), anteriormente neste artigo e, depois, selecione **OK**.
11. Selecione o botão **Anexos** (símbolo de clipe de papel) no canto superior direito da página, e selecione **Abrir** para abrir o arquivo. Revise os valores no documento no Excel.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-vat-declaration"></a>Execute uma declaração IVA para várias entidades legais

Para usar os formatos para relatar a declaração de IVA para um grupo de entidades legais, primeiro você deve configurar os parâmetros específicos do aplicativo dos formatos ER para códigos de imposto de todas as entidades legais necessárias.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Configurar mensagens eletrônicas para coletar dados de impostos de várias entidades legais

Siga estas etapas para configurar mensagens eletrônicas para coletar dados de várias entidades legais.

1. Vá para **Espaços de trabalho** > **Gerenciamento de recursos**.
2. Localize e selecione o recurso **Consultas interempresariais para ações de preencher registros** na lista e selecione **Ativar agora**.
3. Vá até **Imposto** > **Configuração** > **Mensagens eletrônicas** > **Ações de preencher registros**.
4. Na página **Ação de preencher registros**, selecione a linha para **DK Preencher registros de restituição de IVA**.

   Na grade **Configuração de fontes de dados**, um novo campo **Empresa** está disponível. Para registros existentes, este campo mostra o identificador da entidade legal atual.

5. Na grade **Configuração de fontes de dados**, adicione uma linha para cada entidade legal adicional que deve ser incluída no relatório. Em cada nova linha, defina os seguintes campos.

    | Campo                  | Descrição                                                                                                                   |
    |------------------------|-------------------------------------------------------------------------------------------------------------------------------|
    | Nome                   | Insira um valor que o ajudará a compreender a origem deste registro. Por exemplo, insira o **Pagamento de IVA da Subsidiária 1**. |
    | Tipo de item de mensagem      | Selecione **Restituição de IVA**. Esse valor é o único valor que está disponível para todos os registros.                                    |
    | Tipo de conta           | Selecione **Tudo**.                                                                                                               |
    | Nome da tabela mestra      | Especifique **TaxReportVoucher** para todos os registros.                                                                             |
    | Campo de número do documento  | Especifique **Voucher** para todos os registros.                                                                                      |
    | Campo de data do documento    | Especifique **TransDate** para todos os registros.                                                                                    |
    | Campo de conta do documento | Especifique **TaxPeriod** para todos os registros.                                                                                    |
    | Empresa                | Selecione o ID da entidade legal.                                                                                            |
    | Consulta do usuário             | Esta caixa de seleção é selecionada automaticamente quando você define critérios selecionando **Editar consulta**.                                 |

6. Para cada nova linha, selecione **Editar consulta** e especifique um período de liquidação relacionado para a entidade legal especificada no campo **Empresa** na linha.

Quando a configuração é concluída, a função **Coletar dados** na página **Mensagens eletrônicas** reúne os pagamentos de impostos de todas as entidades legais definidas por você.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
