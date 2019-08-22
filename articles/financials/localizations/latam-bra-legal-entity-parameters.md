---
title: Parâmetros para entidades legais no Brasil
description: Para coletar e enviar demonstrativos de imposto que relatem o desempenho, uma entidade legal brasileira requer informações fiscais específicas. Este tópico explica como definir os parâmetros para especificar estas informações.
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Accountant_BR, AccountantElectronicAddress_BR, AccountantPostalAddress_BR, BrazilParameters, FiscalEstablishment_BR, FiscalEstablishmentGroup_BR
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 269404
ms.assetid: af0951b7-078d-49ea-9655-1037dbd0bfe1
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e88eda1464a6997964be3e1382650a1f9d60cb3b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849379"
---
# <a name="parameters-for-legal-entities-in-brazil"></a>Parâmetros para entidades legais no Brasil

[!include [banner](../includes/banner.md)]

Para coletar e enviar demonstrativos de imposto que relatem o desempenho, uma entidade legal brasileira requer informações fiscais específicas. Este tópico explica como definir os parâmetros para especificar estas informações.

<a name="brazilian-legal-entity-overview"></a>Visão geral da entidade legal brasileira
-------------------------------

Uma entidade legal brasileira está organizada por estabelecimentos fiscais que funcionam da mesma forma e está nas mesmas operações de uma ramificação. Há um estabelecimento fiscal principal que é considerado a matriz e os estabelecimentos fiscais relacionados que estão localizados em outros estados ou fora do Brasil. A ilustração a seguir mostra a estrutura de uma entidade legal brasileira e os estabelecimentos fiscais relacionados. 

[![estrutura de uma entidade legal brasileira e dos estabelecimentos fiscais relacionados](./media/bralegalentity-236x300.png)](./media/bralegalentity.png)

## <a name="fiscal-establishments"></a>Estabelecimentos fiscais
Um estabelecimento fiscal é uma localização de uma entidade legal, como subsidiária, filial, fábrica, centro de distribuição, depósito ou loja, que requer um número de inscrição dos impostos do Cadastro Nacional da Pessoa Jurídica (CNPJ) ou da Inscrição Estadual (IE). Uma entidade legal pode ter vários estabelecimentos fiscais. Os estabelecimentos fiscais emitem e recebem notas fiscais e avaliam e pagam os impostos. Você pode executar estas tarefas:

-   Criar grupos de estabelecimentos fiscais e estabelecimentos fiscais.
-   Especificar um estabelecimento fiscal para um site. O endereço do site é atualizado com o endereço de estabelecimento fiscal.
-   Configurar os tipos de documento fiscal que indicam o tipo de documento fiscal que é usado para transações de compra e venda entre estabelecimentos fiscais.
-   Especificar uma matriz de impostos para um grupo de estabelecimentos fiscais. O Código Fiscal de Operações e Prestações (CFOP) que você pode selecionar depende do grupo de estabelecimentos fiscais. Os grupos de impostos que estão disponíveis dependem do grupo de estabelecimentos fiscais e do código CFOP que você seleciona.
-   Criar e lançar uma ordem de venda especificando sites para linhas da ordem de venda. Os códigos de CFOP e os tipos de documentos fiscais que você pode selecionar para as linhas da ordem de vendas dependem dos estabelecimentos fiscais dos sites. Os grupos de impostos e os grupos de impostos de itens para as linhas da ordem de venda são atualizados com base nas matrizes de impostos que são associadas aos estabelecimentos fiscais dos sites por meio de grupos de estabelecimentos fiscais.
-   Criar e lançar uma fatura de texto livre para um estabelecimento fiscal. Os códigos CFOP selecionados para as linhas da fatura de texto livre dependem do estabelecimento fiscal. Os grupos de impostos e os grupos de impostos de itens para as linhas da fatura de texto livre são atualizadas com base nas matrizes de impostos que são associadas aos estabelecimentos fiscais dos sites por meio de grupos de estabelecimentos fiscais.
-   Criar e lançar uma ordem de compra especificando sites que estão anexados aos estabelecimentos fiscais para as linhas da ordem de compra. Os grupos de impostos e os grupos de impostos de itens para as linhas da ordem de compra são atualizados com base nas matrizes de impostos que são associadas aos estabelecimentos fiscais dos sites por meio de grupos de estabelecimentos fiscais.

> [!NOTE]
>  Você cria e atribui o endereço na página **entidades legais**, e o atribui ao estabelecimento fiscal. Você pode atribuir somente um endereço ao estabelecimento fiscal. Para cada estabelecimento fiscal, insira os seguintes IDs de registro de impostos e informações fiscais.

| Campo        | descrição                                                                                                                                       |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| **CNPJ/CPF** | Insira o número de inscrição de contribuinte ou CNPJ (Cadastro Nacional da Pessoa Jurídica/CPF (Cadastro de Pessoas Físicas) da entidade legal.    |
| **CCM**      | Insira o número de registro municipal ou CCM (Cadastro de Contribuinte Mobiliário) da entidade legal.                                       |
| **IE**       | Insira o número de inscrição do estado ou IE (Inscrição Estadual) da entidade legal.                                                             |
| **CNAE**     | Insira o código de classificação nacional ou CNAE (Classificação Nacional de Atividades Econômicas), da atividade econômica da entidade legal. |

### <a name="closed-warehouse"></a>Depósito fechado

| Campo                   | descrição                                                                                                                   |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| **O depósito está fechado?** | Indique se o depósito está fechado para negócios. Geralmente, os depósitos fechados têm regras e validações específicas de impostos. |
| **Emitente de venda**        | O estabelecimento fiscal que faz vendas somente para o estabelecimento fiscal de depósito.                                        |

### <a name="tax-substitution"></a>Substituição tributária

Esta seção é usada para identificar a ID de registro de impostos quando a empresa tem registros em outro estado. Quando este registro existe, ele também permite que a empresa crie a apuração do imposto ICMS-ST.

| Campo     | descrição                                                                       |
|-----------|-----------------------------------------------------------------------------------|
| **Estado** | O estado em que a ID do registro está localizada.                                   |
| **IE**    | O código de registro de autoridade fiscal estadual para o IE do estabelecimento fiscal. |

### <a name="nf-e-and-nfc-e-federal"></a>NF-e e NFC-e federal

Você pode configurar informações e certificados usados em notas fiscais eletrônicas (NF-e) e em notas fiscais eletrônicas para o consumidor (NFC-e).

| Botão                     | descrição                                                      |
|----------------------------|------------------------------------------------------------------|
| **Visualizar serviços Web de NF-e** | Mostra os serviços Web disponíveis para cada tipo de evento.          |
| **Configurar o CSC**          | Configura a criptografia de CSC, inserindo o token de CSC e o CSC. |

#### <a name="nf-e-web-service"></a>Serviço Web de NF-e

| Campo                               | descrição                                                          |
|-------------------------------------|----------------------------------------------------------------------|
| **Ambiente**                     | Especifica se o ambiente é de teste ou de produção. |
| **A versão do recurso de NF-e** | Insira a versão do layout de NF-e a ser usado.                                |
| **Autoridade fiscal**                       | Insira a autoridade fiscal a ser usada para aprovar a NF-e.               |

#### <a name="nfc-e-web-service"></a>Serviço Web de NFC-e

| Campo                                | descrição                                                          |
|--------------------------------------|----------------------------------------------------------------------|
| **Ambiente**                      | Especifica se o ambiente é de teste ou de produção. |
| **A versão do recurso de NFC-e** | Insira a versão do layout de NFC-e a ser usada.                               |
| **Autoridade**                        | Insira a autoridade fiscal a ser usada para aprovar a NFC-e.              |

#### <a name="email-templates"></a>Modelos de email

| Campo                 | descrição                                                         |
|-----------------------|---------------------------------------------------------------------|
| **NFC-e Aprovada**    | Digite o modelo de email criado anteriormente para NFC-e aprovada.     |
| **NF-e aprovada**     | Digite o modelo de email criado anteriormente para NF-e aprovada.      |
| **NF-e cancelada**     | Digite o modelo de email criado anteriormente para NF-e aprovada.      |
| **Carta de correção** | Digite o modelo de email criado anteriormente para cartas de correção. |

#### <a name="security-page-contingency"></a>Contingência da página de segurança

| Campo                   | descrição                                                 |
|-------------------------|-------------------------------------------------------------|
| **Formulário de segurança pré-impresso** | Selecione esta opção se a página de segurança for pré-impressa. |

#### <a name="danfe"></a>DANFE

| Campo                                             | descrição                                                                                |
|---------------------------------------------------|--------------------------------------------------------------------------------------------|
| **Anexar o DANFE-NFC-e ao email como arquivo PDF** | Selecione esta opção se o DANFE NFC-e for enviado como um anexo do email da NFC-e.  |
| **Anexar DANFE como arquivo PDF ao e-mail**         | Selecione esta opção se o DANFE tiver que ser enviado como um anexo do email da NF-e.         |
| **Imprimir DANFE quando a NF-e for aprovada**             | Selecione esta opção se o DANFE tiver que ser impresso quando a NF-e for automaticamente aprovada. |

#### <a name="xml-document"></a>Documento XML

| Campo                              | descrição                                                                          |
|------------------------------------|--------------------------------------------------------------------------------------|
| **Validar esquema XML no lançamento** | Selecione esta opção se o esquema XML tiver que ser validado durante o processo de lançamento. |

#### <a name="nf-e-receipt"></a>NF-e Recebimento

| Campo                                          | descrição                                                                       |
|------------------------------------------------|-----------------------------------------------------------------------------------|
| **Lançar somente NF-e com chaves de acesso válidas** | Selecione esta opção somente se a NF-e com as chaves válidas tiverem que ser lançadas.            |
| **Não postar NF-e se o XML não corresponder com a fatura**   | Selecione esta opção para bloquear a NF-e se o XML não corresponder ao esquema. |

#### <a name="fci"></a>FCI

| Campo                                    | descrição                                                                                        |
|------------------------------------------|----------------------------------------------------------------------------------------------------|
| **FCI se aplica a operações internas** | Selecione esta opção se a FCI for aplicada nas operações que ocorrem entre os diferentes estados. |

### <a name="tax-registration-numbers"></a>Números de registro de imposto

Depois que uma entidade legal brasileira for criada, e o estabelecimento fiscal for criado com o endereço brasileiro relacionado, os seguintes números de registro de impostos aparecem na entidade legal. 
> [!NOTE]
>  Os seguintes campos de registro de imposto pertencem ao endereço principal, pois as IDs de registro de impostos são criadas e atualizadas em cada estabelecimento fiscal/endereço.

| Campo        | descrição                                                                            |
|--------------|----------------------------------------------------------------------------------------|
| **CNPJ/CPF** | O número de inscrição de contribuinte (CNPJ/CPF) da entidade legal.                       |
| **CCM**      | O número de inscrição municipal (CCM) da entidade legal.                           |
| **IE**       | O número de inscrição estadual (IE) da entidade legal.                                |
| **CNAE**     | O código de classificação nacional (CNAE) da atividade econômica da entidade legal. |

## <a name="brazilian-parameters"></a>Parâmetros brasileiros
Use as informações nas seguintes tabelas para configurar parâmetros na página **Parâmetros brasileiros**.

### <a name="general"></a>Geral

| Campo                                            | descrição                                                                                                                                                         |
|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Código CFPS**                                    | Habilitar o Código Fiscal de Serviço (CFPS) para ativar a operação fiscal de códigos de serviços.                                                        |
| **Dimensão financeira para o centro de custo**          | Especifique a dimensão financeira que representa o centro de custo. Essas informações são usadas para gerar demonstrativos de Sistema Público de Escrituração Digital (SPED). |
| **Dimensão financeira para o estabelecimento fiscal** | Especifique a dimensão financeira que representa o estabelecimento fiscal. Esta informação é usada para gerar as instruções do SPED.                                  |
| **Tipo de Operação da Requisição de compra**          | O tipo de operação padrão usado para requisições de compra.                                                                                                  |
| **Tipo de operação para Solicitações de cotações**       | O tipo de operação padrão usado para solicitações de cotações.                                                                                                |

### <a name="fiscal-document"></a>Nota fiscal

Configurar texto padrão e tipos de produto e documento, das notas fiscais que são emitidas e recebidas na entidade legal brasileira.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Método de pagamento principal</strong></td>
<td>Selecione <strong>Duplicata</strong>, <strong>Cheque</strong>, <strong>Nota promissória</strong>, <strong>Recibo</strong> ou <strong>Outros</strong> como o método de pagamento principal para compras. Se você selecionar <strong>Outros</strong> neste campo, no campo <strong>Descrição</strong>, insira a descrição do método principal de pagamento para compras.</td>
</tr>
<tr class="even">
<td><strong>ID do texto</strong> (No grupo de campos <strong>texto da SUFRAMA para emissão de nota fiscal</strong>)</td>
<td>Selecione o ID de texto do documento fiscal padrão que é impressa em notas fiscais que são emitidas para os clientes da região da Superintendência da Zona Franca de Manaus (SUFRAMA).</td>
</tr>
<tr class="odd">
<td><strong>ID do texto</strong> (No grupo de campos <strong>Texto do imposto retido na fonte para emissão de nota fiscal</strong>)</td>
<td>Selecione a ID do texto da nota fiscal padrão do imposto retido na fonte a ser impresso nas notas fiscais.</td>
</tr>
<tr class="even">
<td><strong>Método de pagamento principal</strong></td>
<td>Selecione <strong>Duplicata</strong>, <strong>Cheque</strong>, <strong>Nota promissória</strong>, <strong>Recibo</strong> ou <strong>Outros</strong> como o método de pagamento principal para vendas. Se você selecionar <strong>Outros</strong> neste campo, no campo <strong>Descrição</strong>, insira a descrição do método principal de pagamento para vendas.</td>
</tr>
<tr class="odd">
<td><strong>Tipo de produto</strong></td>
<td>Selecione o tipo de produto padrão para itens que são usados para consumo. Para um item que é comprado para consumo, você pode selecionar esse tipo de produto no campo <strong>Tipo de produto</strong> na página <strong>Detalhes do produto liberado</strong>.</td>
</tr>
<tr class="even">
<td><strong>Tipo de volume</strong> <strong>Quantidade de volume</strong></td>
<td>O tipo de volume padrão e a quantidade de volume de itens nas notas fiscais.</td>
</tr>
<tr class="odd">
<td><strong>Habilitar data de emissão fixada</strong></td>
<td>Marque esta opção para configurar a data fixa de emissão da nota fiscal fixa dos tipos de notas fiscais.</td>
</tr>
<tr class="even">
<td><strong>Item</strong></td>
<td>Selecione a ID de item usada para lançar notas fiscais de faturas de texto livre.</td>
</tr>
<tr class="odd">
<td><strong>Serviço</strong></td>
<td>Selecione a ID de serviço usada para lançar notas fiscais de faturas de texto livre que têm as linhas na opção <strong>Fatura de serviço</strong> selecionada na seção <strong>Informações fiscais</strong>.</td>
</tr>
<tr class="even">
<td><strong>Tipo de documento</strong></td>
<td>Selecione a ID do tipo de documento padrão para textos das notas fiscais. É possível selecionar um tipo de documento que não é atribuído ao texto de nota fiscal que está associado a uma nota fiscal. <strong>Observação:</strong> Se um texto da nota fiscal estiver associado a um documento fiscal, não será possível modificar o tipo de documento.</td>
</tr>
<tr class="odd">
<td><strong>Item </strong></td>
<td>Selecione a ID de item usada para criar notas fiscais de transferência ou apropriação de imposto.</td>
</tr>
<tr class="even">
<td><strong>Código do imposto para PIS</strong></td>
<td>Selecione o código do imposto padrão para o PIS (Programa de Integração Social) que é usado para notas fiscais de transferência ou apropriação de imposto.</td>
</tr>
<tr class="odd">
<td><strong>Código do imposto para COFINS</strong></td>
<td>Selecione o código do imposto padrão para COFINS (Contribuição para o Financiamento da Seguridade Social) que é usado para notas fiscais de transferência ou apropriação de imposto.</td>
</tr>
<tr class="even">
<td><strong>Modelos de textos da nota fiscal</strong></td>
<td>Selecione a ID do modelo de texto da nota fiscal que é impressa nas notas fiscais complementares.</td>
</tr>
<tr class="odd">
<td><strong>O valor da linha baseia-se em</strong></td>
<td>Selecione se os valores da linha em notas fiscais de importação serão baseados no FOB (Freight on Board) ou CIF (Carriage, Insurance and Freight).</td>
</tr>
<tr class="even">
<td><strong>Campo ID do Texto</strong></td>
<td>Selecione a ID do modelo de texto da nota fiscal que é impressa nas notas fiscais de importação.</td>
</tr>
<tr class="odd">
<td><strong>Código do imposto para COFINS</strong></td>
<td>Selecione o código de imposto padrão para COFINS usado para notas fiscais complementares de imposto.</td>
</tr>
<tr class="even">
<td><strong>campo Código do imposto para PIS</strong></td>
<td>Selecione o código de imposto padrão para PIS usado para notas fiscais complementares de imposto.</td>
</tr>
<tr class="odd">
<td><strong>Unidade</strong></td>
<td>Selecione a unidade padrão a ser usada nas linhas da nota fiscal criadas para transações de hora, despesa, por conta ou projeto de item.</td>
</tr>
<tr class="even">
<td><strong>Taxa básica de imposto</strong></td>
<td>Indica o valor de taxa de impostos para cada regime de apuração de impostos PIS e COFINS. Essas informações ajudam a identificar o regime cumulativo e o regime não cumulativo de cada transação de imposto.
<ul>
<li><strong>Valor básico do imposto PIS no regime acumulação</strong> – Insira a porcentagem de taxa de impostos.</li>
<li><strong>Valor básico do imposto PIS no regime não cumulativo</strong> – Insira a porcentagem de taxa de impostos.</li>
<li><strong>Valor básico do imposto COFINS no regime não cumulativo</strong> – Insira a porcentagem de taxa de impostos.</li>
<li><strong>Valor básico do imposto COFINS no regime não cumulativo</strong> – Insira a porcentagem de taxa de impostos.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Origem (Impostos aproximados)</strong></td>
<td>Indica a origem de informações para a porcentagem de imposto aproximada usada.</td>
</tr>
<tr class="even">
<td><strong>ID do Texto (Impostos aproximados)</strong></td>
<td>Selecione a ID do texto que é impressa nas notas fiscais do usuário final. Essas informações são exigidas pela lei fiscal de transparência, ou Lei da Transparência Fiscal.</td>
</tr>
<tr class="odd">
<td><strong>Usuário final</strong></td>
<td>Selecione se o documento é para um usuário final.</td>
</tr>
<tr class="even">
<td><strong>ID do Texto (FCI)</strong></td>
<td>Selecione a ID do texto que é impressa nas notas fiscais de FCI.</td>
</tr>
<tr class="odd">
<td><strong>ICMS ST</strong></td>
<td>Selecione se a substituição tributária de ICMS deve ser aplicada.</td>
</tr>
</tbody>
</table>

### <a name="taxation-code"></a>Código de tributação

É possível configurar um código de tributação obrigatório para um tipo de imposto.

### <a name="electronic-reporting"></a>Relatório eletrônico

Você pode configure o tipo de relatório eletrônico e o mapeamento de modelo relacionado usado para gerar o relatório.

| Campo             | descrição                                                                                                                                                                                                                                     |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Tipo**          | O tipo de relatório. **NF-e de Serviços** é o tipo que está disponível para gerar notas fiscais de serviço.                                                                                                                                         |
| **Mapeamento de modelo** | Especifique o modelo a ser usado. O modelo para notas fiscais de serviço está disponível no repositório do Microsoft Dynamics Lifecycle Services (LCS). Você pode baixar o modelo de LCS e importá-lo para uma configuração de Relatório eletrônico (ER). |

## <a name="accountant-information"></a>Informações do contador
No Brasil, é necessário especificar os detalhes do contador para o relatório de imposto no arquivo de texto fiscal SPED mensalmente, de forma que as autoridades fiscais tenham um registro da pessoa que é responsável pelo relatório de imposto. Na página **Detalhes do contador**, insira as seguintes informações.

| Campo                   | descrição                                                                                                                |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------|
| **CPF**                 | O número de CPF do contador.                                                                                |
| **CNPJ**                | O CNPJ da empresa do contador, se uma outra empresa fizer a contabilidade.                                              |
| **CRC**                 | O número de registro de contador no Conselho Regional de Contabilidade (CRC). |
| **Estado emissor do CRC**    | O estado no qual o documento CRC foi emitido.                                                                               |
| **Data de validade do CRC** | A data de validade do documento CRC.                                                                                   |





