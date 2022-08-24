---
title: Declaração de IVA (Alemanha)
description: Este artigo descreve como configurar e gerar uma declaração de IVA (imposto sobre valor agregado) antecipada para a Alemanha no formato XML oficial.
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 8ee288a1ec7ae950bdff9da7d373e29daef74d3c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269394"
---
# <a name="vat-declaration-germany"></a>Declaração de IVA (Alemanha)

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar e gerar uma declaração de IVA (imposto sobre valor agregado) antecipada para a Alemanha no formato XML oficial. Este artigo também explica como visualizar a declaração de IVA no Microsoft Excel.

Para gerar automaticamente o relatório, crie códigos de impostos suficientes para manter uma contabilização de IVA antecipada para cada caixa na declaração de IVA antecipada. Além disso, nos parâmetros específicos do aplicativo do formato de relatório eletrônico (ER) para a declaração de IVA antecipada, associe os códigos de imposto com o resultado da pesquisa para as caixas na declaração de IVA.

Para a Alemanha, você deve configurar a **Pesquisa de campos de relatório**. Para obter mais informações sobre como configurar parâmetros específicos do aplicativo, consulte a seção [Configurar parâmetros específicos do aplicativo para campos de declaração de IVA](#set-up-application-specific-parameters-for-vat-declaration-fields) mais adiante neste artigo.

Na tabela a seguir, a coluna "Resultado da pesquisa" mostra o resultado da pesquisa pré-configurado para uma linha de declaração de IVA específica no formato da declaração de IVA. Use essas informações para associar corretamente os códigos de imposto ao resultado da pesquisa e com a linha da declaração de IVA.

### <a name="vat-declaration-overview"></a><a name="vat-declaration-overview"></a>Visão geral da declaração de IVA

A declaração de IVA antecipada na Alemanha contém as informações a seguir.

**SEÇÃO – ENTREGAS E OUTROS SERVIÇOS**

**Vendas tributáveis**

| Linha | Caixa – base de impostos | Caixa - valor do imposto | Descrição                                                                                                                                      | Resultado da pesquisa                                                                             |
|-----|----------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 20  | 81             | Sem código     | Vendas tributáveis com uma taxa de imposto de 19%.                                                                                                       | 20-TaxableSalesStandard</br>73-BadDebtsWriteOffStandard (81/50) – com sinal de menos             |
| 21  | 86             | Sem código     | Vendas tributáveis com uma taxa de imposto de 7%.                                                                                                        | 21-TaxableSalesReduced</br>73-BadDebtsWriteOffReduced (86/50) – com sinal de menos               |
| 22  | 35             | 36               | Vendas tributáveis com outras taxas de imposto.                                                                                                                | 22-TaxableSalesOtherRates</br>73-BadDebtsWriteOffOtherRates (35/36/50) – com sinal de menos      |
| 23  | 77             | *Nenhum valor de imposto*  | Entregas de empresas agrícolas e florestais, de acordo com o §24 da UStG (Lei de IVA da Alemanha) para clientes que têm um número de ID de IVA. | 23-EUSalesAverageRate24</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50) – com sinal de menos |
| 24  | 76             | 80               | Vendas para as quais um imposto deve ser pago, de acordo com o §24 de UStG (produtos de serralheria, bebidas e líquidos alcoólicos).                                | 24-SalesAverageRate24</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50)                    |

**Vendas isentas de imposto com dedução de imposto de entrada**

| Linha | Caixa – base de impostos | Caixa - valor do imposto | Descrição                                                                       | Resultado da pesquisa                       |
|-----|----------------|------------------|-----------------------------------------------------------------------------------|-------------------------------------|
| 26  | 41             | *Nenhum valor de imposto*  | Entregas entre comunidades a clientes que têm uma ID de IVA.                       | 26-EUSales                          |
| 27  | 44             | *Nenhum valor de imposto*  | Entregas entre comunidades de novos veículos a compradores que não têm uma ID de IVA.    | 27-EUSalesNewVehicles               |
| 28  | 49             | *Nenhum valor de imposto*  | Entregas entre comunidades de novos veículos fora da empresa.                     | 28-EUSalesNewVehiclesOutsideCompany |
| 29  | 43             | *Nenhum valor de imposto*  | Outras vendas isenta de impostos que têm uma dedução de imposto de entrada, como entregas de exportação. | 29-ExportOtherTaxFreeSales          |

**Vendas isentas de imposto sem dedução de imposto de entrada**

| Linha | Caixa – base de impostos | Caixa - valor do imposto | Descrição                                            | Resultado da pesquisa                           |
|-----|----------------|------------------|--------------------------------------------------------|-----------------------------------------|
| 30  | 48             | *Nenhum valor de imposto*  | Vendas isenta de imposto que não têm dedução de imposto de entrada. | 30-TaxFreeSalesWithoutInputTaxDeduction |

**Aquisições internas na comunidade**

| Linha | Caixa – base de impostos | Caixa - valor do imposto | Descrição                                                                                                                   | Resultado da pesquisa                                                    |
|-----|----------------|------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| 33  | 91             | *Nenhum valor de imposto*  | Aquisições internas na comunidade isentas de impostos de alguns objetos e investimento em ouro.                                                    | 33-TaxFreeEUPurchase                                             |
| 34  | 89             | Sem código     | Aquisições da comunidade interna tributável por uma taxa de imposto de 19%.                                                             | 34-EUPurchaseStandard</br>34-UseTaxEUPurchaseStandard (89/61)        |
| 35  | 93             | Sem código     | Aquisições da comunidade interna tributável por uma taxa de imposto de 7%.                                                              | 35-EUPurchaseReduced</br>35-UseTaxEUPurchaseReduced (93/61)          |
| 36  | 95             | 98               | Aquisições da comunidade interna tributável por outras taxas de impostos.                                                                      | 36-EUPurchaseOtherRates</br>36-UseTaxEUPurchaseOtherRates (95/98/61) |
| 37  | 94             | 96               | Aquisições de comunidade interna tributável de novos veículos de fornecedores que não têm um número de ID de IVA, na taxa de imposto geral. | 37-EUPurchaseVehicles</br>37-UseTaxEUPurchaseVehicles (94/96/61)     |

**SEÇÃO – BENEFICIÁRIO COMO DEVEDOR DE IMPOSTO**

| Linha | Caixa – base de impostos | Caixa - valor do imposto | Descrição                                                                        | Resultado da pesquisa                                                                                        |
|-----|----------------|------------------|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 40  | 46             | 47               | Outros serviços de um empresário, com base no restante da área da Comunidade.        | 40-BeneficiaryTaxDebtor</br>40-UseTaxBeneficiaryTaxDebtor (46/47/66)                                                                              |
| 41  | 73             | 74               | Vendas que estão na seção 13b (2). nº 3 de UStG.                               | 41-BeneficiaryTaxDebtorRealEstateTransfer</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67) |
| 42  | 84             | 85               | Outros serviços que estão na seção 13b (2). nº 1, 2 e 4 a 12 de UStG. | 42-BeneficiaryTaxDebtorOther</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                           |

**SEÇÃO – INFORMAÇÕES SUPLEMENTARES SOBRE VENDAS**

| Linha | Caixa – base de impostos  | Caixa - valor do imposto | Descrição                                                                                                | Resultado da pesquisa                                                                                    |
|-----|-----------------|------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| 48  | 42              | *Nenhum valor de imposto*  | Entregas pelo primeiro cliente no caso de transações triangulares da comunidade.                   | 48-DeliveriesFirstCustomerEUTriangular                                                           |
| 49  | 60              | *Nenhum valor de imposto*  | Vendas tributáveis do empreendedor de execução para as quais o destinatário do serviço deve o imposto. | 49-SalesServicesReverseCharge                                                                    |
| 50  | 21              | *Nenhum valor de imposto*  | Outros serviços não tributáveis.                                                                                | 50-OtherServicesNonTaxable                                                                       |
| 51  | 45              | *Nenhum valor de imposto*  | Outras vendas não tributáveis quando o local do desempenho não estiver na Alemanha.                                    | 51-OtherSalesNonTaxable                                                                          |
| 52  | *Nenhum valor de imposto* | *Nenhum valor de imposto*  | IVA.                                                                                                       | Linha 20 + Linha 21 + Linha 22 + Linha2 4 + Linha 34 + Linha 35 + Linha 36 + Linha 37 + Linha 40 + Linha 41 + Linha 42 |

**SEÇÃO – IMPOSTO SOBRE ENTRADA DEDUTÍVEL**

| Linha | Caixa - valor do imposto | Descrição                                                                                                | Resultado da pesquisa                                                                                                                                                                |
|-----|------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 55  | 66               | Valores de imposto da fatura de entrada de outras empresas, serviços e transações triangulares dentro da comunidade.     | 55-InputTax 40-UseTaxBeneficiaryTaxDebtor (46/47/66)</br>74-BadDebtsWriteOffInputTax (66/37) – com sinal de menos                                                                   |
| 56  | 61               | Valores de imposto de entrada da aquisição interna na comunidade de mercadorias.                                           | 56-InputTaxEUPurchase 34-UseTaxEUPurchaseStandard (89/61)</br>35-UseTaxEUPurchaseReduced (93/61)</br>36-UseTaxEUPurchaseOtherRates (95/98/61)</br>37-UseTaxEUPurchaseVehicles (94/96/61) |
| 57  | 62               | Imposto de importação incorrido.                                                                                 | 57-InputTaxImport                                                                                                                                                            |
| 58  | 67               | Valores de impostos de entrada de serviços de acordo com o significado do §13b de UStG.                                        | 58-InputTaxServices</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67)</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                                                 |
| 59  | 63               | Valores de imposto de entrada calculados de acordo com as taxas médias gerais.                                  | 59-InputTaxAverageRates</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37) – com sinal de menos                                                                                    |
| 60  | 59               | Dedução de imposto de entrada para entregas na comunidade de novos veículos fora de uma empresa e de pequenas empresas. | 60-InputTaxEUPurchaseNewVehicles</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37) – com sinal de menos                                                                  |
| 61  | 64               | Correção da dedução de imposto de entrada.                                                                     | 61-InputTaxCorrection                                                                                                                                                        |
| 62  | \-               | O valor restante.                                                                                      | Linha 52 – Linha 55 – Linha 56 – Linha 57 – Linha 58 – Linha 50 – Linha 60 – Linha 61                                                                                                        |

**SEÇÃO – OUTROS VALORES DE IMPOSTO**

| Linha | Caixa - valor do imposto | Descrição                                                                                                                                                                                                                                                         | Resultado da pesquisa                                 |
|-----|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 64  | 65               | Imposto em decorrência de uma alteração no formulário de tributação e imposto adicional sobre pagamentos de entrada tributados por causa de alteração na taxa de imposto.                                                                                                                                        | 64-AdditionalTaxDueChangeTaxRate              |
| 65  | 69               | Valores de impostos incorretos ou não justificados que são exibidos em faturas e valores de impostos que são devidos de acordo com a seção 6a (4), seção 17 (1) frase 7, ou seção 25b (2) de UStG ou que são devidos por uma empresa terceirizada ou um depositário. | 65-TaxDecreaseCorrection                      |
| 67  | 39               | Dedução do pagamento antecipado especial fixo para extensão permanente. Em geral, essa linha é preenchida somente com a última notificação antecipada do período de imposto.                                                                                                  | Parâmetro de entrada do usuário na caixa de diálogo relatório |
| 68  | 83               | O pagamento de imposto antecipado restante e o excesso. Inclua um sinal de menos na frente do valor.                                                                                                                                                          | Linha 62 + Linha 64 – Linha 65 – Linha 66             |

**SEÇÃO – INFORMAÇÕES SUPLEMENTARES SOBRE REDUÇÕES**

| Linha | Caixa – base de impostos | Caixa - valor do imposto | Descrição                                                            | Resultado da pesquisa                                                                                                                                                                                                    |
|-----|----------------|------------------|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 73  | 50             | \-               | Redução da base do imposto nas linhas 20 a 24.                      | 73-BadDebtsWriteOffStandard (81/50)</br>73-BadDebtsWriteOffReduced (86/50)</br>73-BadDebtsWriteOffOtherRates (35/36/50)</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50)</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50) |
| 74  | \-             | 37               | Redução dos valores de imposto de entrada dedutível nas linhas 55, 59 e 60. | 74-BadDebtsWriteOffInputTax (66/37)</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37)</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37)                                                                     |

#### <a name="purchase-reverse-charge-vat"></a>IVA de encargos revertidos de compra

Se você configurar códigos de imposto para lançar o IVA de encargos revertidos de entrada usando o imposto sobre o uso, associe os códigos de imposto ao resultado da **Pesquisa de campos de Relatório** que contém "UseTax" no nome.

Como alternativa, você pode configurar dois códigos de impostos separados: um para IVA devido e um para dedução de IVA. Em seguida, associe cada código aos resultados de pesquisa correspondentes da **Pesquisa de campos de Relatório**.

Por exemplo, para aquisições tributáveis na comunidade a uma taxa padrão, configure o código do imposto **UT_S_EU** com imposto sobre o uso e associe-o ao resultado da pesquisa **34-UseTaxEUPurchaseStandard** do resultado da pesquisa da **Pesquisa de campos de Relatório**. Nesse caso, os valores que usam o código do imposto **UT_S_EU** são refletidos nas caixas 089 e 061 (linhas 34 e 56).

Como opção, configure dois códigos de impostos:

  - **VAT_S_EU**, que tem um valor de taxa de imposto de -19%
  - **InVAT_S_EU**, que tem um valor de taxa de imposto de -19%

Associe os códigos aos resultados de pesquisa da **Pesquisa de campos de relatório** da seguinte forma:

  - Associe **VAT_S_EU** ao resultado da pesquisa **34-EUPurchaseStandard**.
  - Associe **InVAT_S_EU** ao resultado da pesquisa **56-InputTaxEUPurchase**.

Nesse caso, os valores que usam o código do imposto **VAT_S_EU** são refletidos na caixa 089 (linha 34). Valores que usam o código do imposto **InVAT_S_EU** são refletidos na caixa 061 (linha 56).

Para obter mais informações sobre como configurar IVA de encargos revertidos, consulte [Encargos revertidos](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configurar parâmetros do sistema

Para gerar uma declaração de IVA, você deve configurar o número do imposto (Steuernummer) da sua organização.

1. Acesse **Administração da organização** > **Organizações** > **Entidades legais**.
2. Selecione a entidade legal e **IDs de Registro**.
3. Selecione ou crie o endereço na Alemanha e, em seguida, na FastTab **ID de registro**, selecione **Adicionar**.
4. No campo **Tipo de registro**, selecione o tipo de registro dedicado à Alemanha e que usa a categoria de registro **ID da empresa (COID)**.
5. No campo **Número de registro**, informe o número do imposto.
6. Na guia **Geral**, no campo **Efetivo**, insira a data em que o número entra em vigor.

Para obter mais informações sobre como configurar categorias de registro e tipos de registro, consulte [IDs de Registro](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-for-germany"></a>Configurar uma declaração de IVA para a Alemanha

### <a name="import-er-configurations"></a>Importar configurações ER

Abra o espaço de trabalho **Relatório eletrônico** e importe as seguintes versões ou posteriores desses formatos de ER:

   - Declaração de IVA no Excel (DE).versão.101.16.12.xml
   - XML da Declaração de IVA (DE).versão.101.16.xml

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a>Configurar parâmetros específicos do aplicativo para campos de declaração de IVA

Para gerar automaticamente uma declaração de IVA, associe os códigos de imposto no aplicativo e os resultados da pesquisa na configuração ER.

> [!NOTE]
> Recomendamos habilitar o recurso **Usar parâmetros específicos do aplicativo das versões anteriores de formatos ER** no espaço de trabalho **Gerenciamento de recursos**. Quando o recurso está habilitado, os parâmetros configurados para a versão anterior de um formato ER se tornarão aplicáveis automaticamente à versão posterior do mesmo formato. Se o recurso não estiver habilitado, você deverá configurar explicitamente parâmetros específicos do aplicativo para cada versão de formato. O recurso **Usar parâmetros específicos do aplicativo das versões anteriores de formatos ER** está disponível no espaço de trabalho **Gerenciamento de recursos** a partir da versão 10.0.23 do Finance. Para obter mais informações sobre como configurar os parâmetros de um formato ER para cada entidade legal, consulte [Configurar os parâmetros de um formato ER de acordo com a entidade legal](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Siga estas etapas para definir quais códigos de impostos geram quais caixas na declaração de IVA.

1. Vá para **Espaços de Trabalho** > **Relatório eletrônico** e selecione **Configurações de relatórios**.
2. Selecione a configuração **XML da Declaração de IVA (DE)** e, em seguida, selecione **Configurações \> Configuração de parâmetros específicos do aplicativo**.
3. Na página **Parâmetros específicos do aplicativo**, na FastTab **Pesquisas**, selecione **Pesquisa de campos de relatório**.
4. Na FastTab **Condições**, defina os campos a seguir para associar os códigos de imposto e os campos de relatório.

    | Campo                  | Descrição                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Resultado da pesquisa          | Selecione o valor do campo do relatório. Para obter mais informações sobre os valores e suas atribuições às linhas da declaração de IVA, consulte a seção [visão geral da declaração de IVA](#vat-declaration-overview) anteriormente contida neste artigo.                                                                                               |
    | Código do imposto               | Selecione o código do imposto a ser associado ao campo do relatório. As transações de imposto lançadas que usam o código de imposto selecionado serão coletadas na caixa de declaração apropriada. Recomendamos que você separe os códigos de impostos de tal forma que um código de imposto gera valores em apenas uma caixa de declaração. |
    | Classificador de transação | Se você criou códigos de impostos suficientes para determinar uma caixa de declaração, selecione **\*Não em branco\***. Se você não criou códigos de imposto suficientes para que um código de imposto gere valores em apenas uma caixa de declaração, você pode configurar um classificador de transação. Os seguintes classificadores de transação a seguir estão disponíveis:</br>-   **Compra**</br>-   **PurchaseExempt** (compra isenta de impostos)</br>-   **PurchaseReverseCharge** (imposto a receber de um encargo revertido de compra)</br>-   **Vendas**</br>-   **SalesExempt** (venda isenta de impostos)</br>-   **SalesReverseCharge** (imposto sobre o encargo revertido de compra ou um encargo revertido de venda)</br>-   **Imposto sobre o uso**. </br>Para cada classificador de transação, também está disponível um classificador para a nota de crédito. Por exemplo, um desses classificadores é **PurchaseCreditNote** (nota de crédito de compra).</br>Certifique-se de criar duas linhas para cada código de imposto: um que tenha o valor do classificador da transação e um que tenha o classificador da transação para o valor da nota de crédito. |

    > [!NOTE]
    > Associe todos os códigos de imposto a resultados de pesquisa. Se nenhum código de imposto não gerar valores na declaração de IVA, associe-os ao **Outro** resultado de pesquisa.

    ![Página de parâmetros específicos do aplicativo](media/69ecb881f12819259ca166b9b98b8303.jpg)

5. No campo **Estado**, altere o valor para **Concluído**.
6. No Painel de Ações, selecione **Exportar** para exportar as configurações dos parâmetros específicos do aplicativo.
7. Selecione a configuração **Declaração de IVA no Excel (DE)** e, em seguida, no Painel de Ações, selecione **Importar** para importar os parâmetros que você configurou para **XML da Declaração de IVA (DE)**.
8. No campo **Estado**, selecione **Concluído**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Configurar o formato de relatório de IVA para valores de visualização no Excel

1. No espaço de trabalho **Gerenciamento de recursos**, localize e ative o recurso **Relatórios de formato de declaração de IVA**.
2. Vá para **Contabilidade** > **Configuração** > **Parâmetros de contabilidade**.
3. Na guia **Imposto**, na FastTab **Opções de imposto**, no campo **Mapeamento de formatos da declaração de IVA**, selecione **Declaração de IVA no Excel (DE)**.

   Esse formato é impresso quando você executa o relatório **Imposto para o período de liquidação**. Também é impresso quando você seleciona **Imprimir** na página **Pagamentos de impostos**.

4. Na página **Autoridades de imposto**, selecione a autoridade de imposto e, no campo **Layout do relatório**, selecione **Padrão**.

Se você estiver configurando a declaração de IVA em uma entidade legal que tenha [vários registros de IVA](emea-reporting-for-multiple-vat-registrations.md), siga estas etapas:

1. Vá para **Contabilidade** > **Configuração** > **Parâmetros de contabilidade**.
2. Na guia **Imposto**, na FastTab **Relatório eletrônico para países/regiões**, na linha de **DEU**, selecione o formato de ER **Declaração de IVA no Excel (DE)**.

## <a name="set-up-electronic-messages"></a>Configurar mensagens eletrônicas

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Baixar e importar o pacote de dados que contém exemplos de configurações para mensagens eletrônicas

O pacote de dados contém configurações de mensagens eletrônicas usadas para gerar a declaração de IVA no formato XML e visualizá-lo no Excel. Você pode estender essas configurações ou criar suas próprias. Para obter mais informações sobre como trabalhar com mensagens eletrônicas e criar suas próprias configurações, consulte [Mensagens eletrônicas](../general-ledger/electronic-messaging.md).

1. No [Microsoft Dynamics Lifecycle Services(LCS)](https://lcs.dynamics.com/v2), na biblioteca de ativo Compartilhado, selecione **Pacote de dados** como o tipo de ativo e baixe **Pacote EM de declaração de IVA DE**. O nome do arquivo baixado é **Pacote EM de declaração de IVA DE. zip**.
2. No Dynamics 365 Finance, no espaço de trabalho **Gerenciamento de dados**, selecione **Importar**.
3. Na FastTab **Importar**, no campo **Nome do grupo**, digite um nome para o trabalho.
4. Na guia rápida **Entidades selecionadas**, selecione **Adicionar arquivo**.
5. Na caixa de diálogo **Adicionar arquivo**, verifique se o campo **Formato de dados de origem** está definido como **Pacote**, selecione **Carregar e adicionar** e selecione o arquivo zip baixado anteriormente.
6. Selecione **Fechar**.
7. Depois que as entidades de dados forem carregadas, no painel de ação, selecione **importar**.
8. Vá para **Imposto** > **Consultas e relatórios** > **Mensagens eletrônicas** > **Mensagens eletrônicas** e valide o processamento de mensagem eletrônica que você importou.

### <a name="configure-electronic-messages"></a>Configurar mensagens eletrônicas

1. Vá até **Imposto** > **Configuração** > **Mensagens eletrônicas** > **Ações de preencher registros**.
2. Selecione a linha para **DE Preencher registros de restituição de IVA** e selecione **Editar consulta**.
3. Use o filtro para especificar os períodos de liquidação a serem incluídos no relatório.
4. Se você deve relatar transações de imposto de outros períodos de liquidação em uma declaração diferente, crie uma nova ação **Preencher registros** e selecione os períodos de liquidação apropriados.

## <a name="preview-the-vat-declaration-in-excel"></a>Visualizar a declaração de IVA no Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>Visualizar a declaração de IVA no Excel a partir do Relatório de imposto para a tarefa periódica do período de liquidação

1. Vá até **Imposto** > **Tarefas periódicas** > **Declarações** > **Impostos** > **Relatar imposto do período de liquidação**.
2. No campo de **Período de liquidação**, selecione um valor.
3. No campo **Versão de liquidação do imposto**, selecione um dos valores a seguir:

    - **Original**: gera um relatório para as transações de impostos do pagamento do imposto original ou antes que o pagamento do imposto seja gerado.
    - **Correções**: gera um relatório para as transações de imposto de todos os pagamentos de imposto subsequentes para o período.
    - **Lista total**: gera um relatório para todas as transações de imposto do período, incluindo o original e todas as correções.

4. No campo **Data inicial**, selecione a data de início do período do relatório.
5. Selecione **OK** e analise o relatório do Excel.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>Liquidar e lançar imposto

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
    > O relatório é gerado somente para a linha de pagamento de imposto selecionada. Se você quiser gerar, por exemplo, uma declaração corretiva que contém todas as correções para o período, ou uma declaração de substituição que contém os dados originais e todas as correções, use a tarefa periódica **Relatar imposto do período de liquidação**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Gerar uma declaração de IVA de mensagens eletrônicas

Ao usar mensagens eletrônicas para gerar o relatório, você pode coletar dados de impostos de várias entidades legais. Para obter mais informações, consulte a seção [Executar uma declaração de IVA para várias entidades legais](#run-a-vat-declaration-for-multiple-legal-entities) mais adiante neste artigo.

O procedimento a seguir aplica-se ao exemplo de processamento de mensagens eletrônicas que você importou da biblioteca de Ativos compartilhados do LCS.

1. Vá para **Imposto** > **Consultas e relatórios** > **Mensagens eletrônicas** > **Mensagens eletrônicas**.
2. No painel esquerdo, selecione **DE Declaração de IVA**.
3. Na FastTab **Mensagens**, selecione **Novo** e, em seguida, na caixa de diálogo **Executar processamento**, selecione **OK**.
4. Selecione a linha da mensagem que é criada, insira uma descrição e especifique as datas inicial e final da declaração.

    > [!NOTE]
    > As etapas 5 a 7 são opcionais.

5. Opcional: na FastTab **Mensagens**, selecione **Coletar dados** e, em seguida, selecione **OK**. Os pagamentos de impostos que foram gerados anteriormente são adicionados à mensagem. Para obter mais informações, consulte a seção [Liquidar e lançar imposto](#settle-and-post-sales-tax) anteriormente neste artigo. Se pular esta etapa, você ainda poderá gerar uma declaração de IVA usando o campo **Versão da declaração de imposto** na caixa de diálogo **Declaração**.
6. Opcional: na FastTab **Itens de mensagem**, revise os pagamentos de impostos que são transferidos para processamento. Por padrão, todos os pagamentos de impostos do período selecionado que não foram incluídos em outras mensagens do mesmo processamento são incluídos.
7. Opcional: selecione **Documento original** para revisar os pagamentos de impostos ou selecione **Excluir** para excluir pagamentos de impostos do processamento. Se pular esta etapa, você ainda poderá gerar uma declaração de IVA usando o campo **Versão da declaração de imposto** na caixa de diálogo **Declaração**.
8. Na FastTab **Mensagens**, selecione **Atualizar status**. Na caixa de diálogo **Atualizar status**, selecione **Pronto para gerar** e, em seguida, selecione **OK**. Verifique se o status da mensagem foi alterado para **Pronto para gerar**.
9. Selecione **Gerar relatório**. Para visualizar os valores da declaração de IVA, na caixa de diálogo **Executar processamento**, selecione **Visualizar relatório** e, em seguida, selecione **OK**.
10. Na caixa de diálogo **Parâmetros de relatório eletrônico**, defina os seguintes campos e selecione **OK**.

    | **Campo**                                   | **Descrição**                                                                                                                                                                                                              |
    |---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Período de liquidação                           | Selecione o período de liquidação. Se você selecionou **Coletar dados** na etapa 5, pode deixar este campo em branco. O relatório será gerado para as transações de imposto incluídas nos pagamentos de impostos coletados. |
    | Versão da declaração de imposto                     | Selecione um dos seguintes valores:</br>-   **Original** – gera um relatório para as transações de impostos do pagamento do imposto original ou antes que o pagamento do imposto seja gerado.</br>-   **Correções** – gera um relatório para as transações de imposto de todos os pagamentos de imposto subsequentes para o período.</br>-   **Lista total** – gera um relatório para todas as transações de imposto do período, incluindo o original e todas as correções.|
    | Representante de imposto | Selecione o participante que é um representante de imposto para declaração de IVA, se aplicável. As informações sobre o participante selecionado são exportadas para o elemento XML **DatenLieferant**. |
    | Pessoa de contato | Selecione uma pessoa na organização que é um fornecedor de dados. As informações sobre a pessoa selecionada são exportadas para o elemento XML **DatenLieferant**. |
    | Devolução corretiva | Selecione **Sim** se esta for a declaração de IVA corretiva. Nesse caso, o elemento XML KZ10 terá um valor de **1**.|
    | Documentos de suporte | Selecione **Sim** se você também enviar documentos de suporte. Nesse caso, o elemento XML KZ22 terá um valor de **1**.|
    | A carta de ordem de débito direto SEPA será revogada como uma exceção| Selecione **Sim** se o mandato de débito direto SEPA foi revogado como uma exceção para esse período anterior ao registro. Por exemplo, por causa das solicitações de compensação. Qualquer saldo restante deve ser pago separadamente. Nesse caso, o elemento XML KZ26 terá um valor de **1**. |
    | Deslocamento do valor de reembolso desejado | Selecione **Sim** se o deslocamento do valor de reembolso desejado ou se o valor de reembolso tiver sido atribuído. Nesse caso, o elemento XML KZ29 terá um valor de **1**. |
    | Extensão permanente de pagamento antecipado especial | Informe o valor de dedução do pagamento antecipado especial fixo para extensão permanente. Esse valor de dedução geralmente é concluído somente no último registro anterior do período de imposto. O valor é exportado na linha 67 (caixa 39) e KZ39 do elemento XML da declaração de IVA. |

11. Selecione **Anexos** no canto superior direito da página e depois **Abrir**.
12. Revise os valores no documento do Excel e selecione **Gerar relatório**.
13. Para gerar uma declaração de IVA no formato XML, na caixa de diálogo **Executar processamento**, selecione **Gerar relatório** e selecione **OK**.
14. Na caixa de diálogo **Parâmetros de relatório eletrônico**, defina os campos como descrito na etapa 10.
15. Selecione **Anexos** no canto superior direito da página, baixe o arquivo e use-o para o seu envio à autoridade fiscal.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a>Execute uma declaração IVA para várias entidades legais

Para usar os formatos para relatar a declaração de IVA para um grupo de entidades legais, primeiro você deve configurar os parâmetros específicos do aplicativo dos formatos ER para códigos de imposto de todas as entidades legais necessárias.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Configurar mensagens eletrônicas para coletar dados de impostos de várias entidades legais

Siga estas etapas para configurar mensagens eletrônicas que coletarão dados de várias entidades legais.

1. Vá para **Espaços de trabalho** > **Gerenciamento de recursos**.
2. Localize e selecione o recurso **Consultas interempresariais para ações de preencher registros** na lista e selecione **Ativar agora**.
3. Vá até **Imposto** > **Configuração** > **Mensagens eletrônicas \> Ações de preencher registros**.
4. Na página **Ação de preencher registros**, selecione a linha para **DE Preencher registros de restituição de IVA**.

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
