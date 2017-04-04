---
title: "Parâmetros para entidades legais em O Brasil"
description: "A coleta e enviar demonstrativos de imposto que se reportam em desempenho, uma entidade legal brasileira requer informações fiscais específicas. Este tópico explica como definir parâmetros para especificar essas informações."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: Accountant_BR, AccountantElectronicAddress_BR, AccountantPostalAddress_BR, BrazilParameters, FiscalEstablishment_BR, FiscalEstablishmentGroup_BR
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269404
ms.assetid: af0951b7-078d-49ea-9655-1037dbd0bfe1
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 3f7d054a59e2bfcc208d569264bcd0d517df2319
ms.lasthandoff: 03/31/2017


---

# <a name="parameters-for-legal-entities-in-brazil"></a>Parâmetros para entidades legais em O Brasil

A coleta e enviar demonstrativos de imposto que se reportam em desempenho, uma entidade legal brasileira requer informações fiscais específicas. Este tópico explica como definir parâmetros para especificar essas informações.

<a name="brazilian-legal-entity-overview"></a>Visão geral de entidade legal brasileira
-------------------------------

Uma entidade legal brasileira está organizada por estabelecimentos fiscais que funcionam da mesma forma e está nas mesmas operações de um ramo. Há um estabelecimento fiscal principal que é considerado o Matriz, os estabelecimentos fiscais relacionadas que estão localizados em outros estados ou fora Brasil. A ilustração a seguir mostra a estrutura de uma entidade legal brasil e de um estabelecimentos fiscais relacionadas. 

[estrutura do![de uma entidade legal brasil e de um estabelecimentos fiscais relacionadas (]. /media/bralegalentity-236x300.png)](. /media/bralegalentity.png)

## <a name="fiscal-establishments"></a>Estabelecimentos fiscais
O estabelecimento fiscal é um local físico de uma entidade legal, como uma subsidiária, uma filial, uma fábrica, um centro de distribuição, um depósito, uma loja, ou que exige número de registro de imposto (IE) de do Cadastro Nacional da Pessoa Jurídica (CNPJ) ou de registro Estadual. Uma entidade legal pode ter vários estabelecimentos fiscais. Os estabelecimentos fiscais emitem e recebem notas fiscais e avaliam e pagam os impostos. Você pode executar estas tarefas:

-   Criar grupos de estabelecimentos fiscais e estabelecimentos fiscais.
-   Especificar um estabelecimento fiscal para um site. O endereço do site é atualizado com o endereço de estabelecimento fiscal.
-   Tipos de documento fiscal de instalação que indicam o tipo de documento fiscal usado para transações de venda e compra entre estabelecimentos fiscais.
-   Especificar uma matriz de impostos para um grupo de estabelecimentos fiscais. O código do Código Fiscal de Operações e Prestações () CFOP que você pode selecionar depende do grupo do estabelecimento fiscal. Os grupos de impostos sobre vendas disponíveis dependem do grupo do estabelecimento fiscal e CFOP do código selecionado.
-   Criar e lançar uma ordem de venda especificando sites para linhas da ordem de venda. Códigos e tipos de documento fiscal CFOP que você pode selecionar para as linhas de ordem de venda dependem de estabelecimentos fiscais sites. Os grupos de impostos sobre vendas e os grupos de impostos de itens para as linhas de ordem de venda são atualizados com base em sede de imposto associadas estabelecimentos fiscais aos sites nos grupos do estabelecimento fiscal.
-   Criar e lançar uma fatura de texto livre para um estabelecimento fiscal. Códigos CFOP que você pode selecionar para as linhas de nota fiscal de texto livre dependem do estabelecimento fiscal. Os grupos de impostos sobre vendas e os grupos de impostos de itens para as linhas de nota fiscal de texto livre são atualizados baseados em sede de imposto associadas estabelecimentos fiscais aos sites nos grupos do estabelecimento fiscal.
-   Criar e lançar uma ordem de compra especificando sites que estão anexados aos estabelecimentos fiscais para as linhas da ordem de compra. Os grupos de impostos sobre vendas e os grupos de impostos de itens para as linhas de ordem de compra são atualizadas com base em sede de imposto associadas estabelecimentos fiscais aos sites nos grupos do estabelecimento fiscal.

> [!NOTE]
>  Criar e atribuir o endereço ** entidades legais ** na página, e atribuí-la o estabelecimento fiscal. Você pode atribuir somente um endereço ao estabelecimento fiscal. Para cada estabelecimento fiscal, insira os seguintes itens e informações do registro de imposto.

| Campo        | descrição                                                                                                                                       |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| **CNPJ/CPF** | Insira o número de registro do contribuinte, ou no Cadastro Nacional da Pessoa Jurídica (/Cadastro) CNPJ de Pessoas Físicas (CPF), a entidade legal.    |
| **CCM**      | Insira o número de registro ou municipais, no Cadastro de contribuinte mobiliário (CCM), a entidade legal.                                       |
| **IE**       | Insira o número de registro do estado, ou no registro, Estadual (IE) de entidade legal.                                                             |
| ** CNAE **     | Insira o código de classificação nacionais, Classificação nacionais ou em Atividades de Econômicas (CNAE), para a atividade econômica de entidade legal. |

### <a name="closed-warehouse"></a>Depósito fechado

| Campo                   | descrição                                                                                                                   |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| **Is closed warehouse** | Indique se o depósito é fechado do negócio. Geralmente, os depósitos fechados tiverem regras e validações específicas de impostos. |
| ** Emissor vendas **        | O estabelecimento fiscal que faz vendas para o estabelecimento fiscal de depósito - somente.                                        |

### <a name="tax-substitution"></a>Substituição tributária

Esta seção é usada para identificar a ID de registro de impostos quando a empresa tem registros em outro estado. Quando o registro também existe, permite que a empresa para criar a previsão de imposto ICMS-ST.

| Campo     | descrição                                                                       |
|-----------|-----------------------------------------------------------------------------------|
| **State** | O estado em que a ID de registro for atingido.                                   |
| **IE**    | O código de registro de autoridade fiscal de IE estado para o estabelecimento fiscal. |

### <a name="nf-e-and-nfc-e-federal"></a>NF-e e NFC-e federal

Configure informações e certificados usados em documentos eletrônico NF-e (federal) e em documento fiscal eletrônico para o NFC -e - consumo (e).

| Botão                     | descrição                                                      |
|----------------------------|------------------------------------------------------------------|
| **View NF-e web services** | Mostre os serviços da Web disponíveis para cada tipo de evento.          |
| **Setup the CSC**          | Configurar a criptografia de CSC inserindo o CSC simbólico e o CSC. |

#### <a name="nf-e-web-service"></a>Serviço Web de NF-e

| Campo                               | descrição                                                          |
|-------------------------------------|----------------------------------------------------------------------|
| ** Ambiente **                     | Especifique se o teste é um ambiente ou um ambiente de produção. |
| **The version of the NF-e feature** | Insira a versão do layout de NF-e a ser usado.                                |
| **Authority**                       | Insira a autoridade fiscal ao aprovar NF-e o uso.               |

#### <a name="nfc-e-web-service"></a>Serviço Web de NFC-e

| Campo                                | descrição                                                          |
|--------------------------------------|----------------------------------------------------------------------|
| ** Ambiente **                      | Especifique se o teste é um ambiente ou um ambiente de produção. |
| **The version of the NFC-e feature** | Insira a versão do layout do NFC -e - e ao uso.                               |
| **Authority**                        | Insira a autoridade fiscal usado para aprovar o NFC -e - e.              |

#### <a name="email-templates"></a>Modelos de email

| Campo                 | descrição                                                         |
|-----------------------|---------------------------------------------------------------------|
| **Approved NFC-e**    | Digite o modelo de email criada anteriormente para NFC -e - e aprovado.     |
| **Approved NF-e**     | Digite o modelo de email criada anteriormente NF-e para aprovado.      |
| **Canceled NF-e**     | Digite o modelo de email criada anteriormente para o NF-e cancelado.      |
| **Correction letter** | Digite o modelo de email criada anteriormente para letras de correção. |

#### <a name="security-page-contingency"></a>Página de contingência de segurança

| Campo                   | descrição                                                 |
|-------------------------|-------------------------------------------------------------|
| ** ** Segurança pré-imprimida | Selecione esta opção se a página de segurança serão pré-impresso. |

#### <a name="danfe"></a>DANFE

| Campo                                             | descrição                                                                                |
|---------------------------------------------------|--------------------------------------------------------------------------------------------|
| **Attach the DANFE NFC-e as a PDF file to email** | Selecione esta opção se o NFC -e - e o DANFE for enviado como um anexo do email do NFC -e - e.  |
| ** Anexar o DANFE como o arquivo PDF para enviar e-mail **         | Selecione esta opção se o DANFE for enviado como em um anexo de NF-e email.         |
| **Print DANFE when NF-e is approved**             | Selecione esta opção se o DANFE é impressa quando o NF-e é automaticamente aprovado. |

#### <a name="xml-document"></a>Documento XML

| Campo                              | descrição                                                                          |
|------------------------------------|--------------------------------------------------------------------------------------|
| **Validate XML schema on posting** | Selecione esta opção se o esquema XML é validado durante o processo de postagem. |

#### <a name="nf-e-receipt"></a>NF-e Recebimento

| Campo                                          | descrição                                                                       |
|------------------------------------------------|-----------------------------------------------------------------------------------|
| **Post only NF-e that have valid access keys** | Selecione esta opção somente se o NF-e com as chaves válidos se for lançado.            |
| **Block NF-e posting if XML does not match**   | Selecione esta opção a postagem para bloquear o NF-e se XML não corresponde ao esquema. |

#### <a name="fci"></a>FCI

| Campo                                    | descrição                                                                                        |
|------------------------------------------|----------------------------------------------------------------------------------------------------|
| **FCI applies to intrastate operations** | Selecione esta opção se o FCI for aplicado nas operações que ocorrem entre os diferentes. |

### <a name="tax-registration-numbers"></a>Números de registro de imposto

Depois de uma entidade legal brasileira será criada, e o estabelecimento fiscal é criado com o endereço brasileiro relacionado, estes números de registro de impostos sobre vendas apareçam na entidade legal. 
> [!NOTE]
>  Os seguintes campos de inscrição municipal pertencem ao endereço principal, pois as IDs de registro de impostos sobre vendas são criadas e atualizados em cada estabelecimento fiscal/endereço.

| Campo        | descrição                                                                            |
|--------------|----------------------------------------------------------------------------------------|
| **CNPJ/CPF** | O número de registro do contribuinte (CNPJ/CPF) a entidade legal.                       |
| **CCM**      | O número de registro (CCM municipal) a entidade legal.                           |
| **IE**       | O número de registro de IE estado () a entidade legal.                                |
| ** CNAE **     | O código de classificação UNIVERSITY (CNAE) para a atividade econômica de entidade legal. |

## <a name="brazilian-parameters"></a>Parâmetros brasileiros
Use as informações nas seguintes tabelas para configurar parâmetros ** parâmetros brasileiros ** na página.

### <a name="general"></a>Geral

| Campo                                            | descrição                                                                                                                                                         |
|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ** Código CFPS **                                    | Habilitar o Código Fiscal de Serviço (CFPS) para ativar a operação códigos fiscal de serviços.                                                        |
| **Financial dimension for cost center**          | Especifique a dimensão financeira que representa o centro de custo. Essas informações são usadas para gerar demonstrativos de Sistema Publico de Escrituração Digital (SPED). |
| **Financial dimension for fiscal establishment** | Especifique a dimensão financeira que representa o estabelecimento fiscal. Esta informação é usada para gerar as instruções do SPED.                                  |
| ** Tipo de operação da requisição **          | O tipo de operação padrão usado para requisições de compra.                                                                                                  |
| ** Solicitações para o tipo de operação cotações **       | O tipo de operação padrão usado para solicitações de cotações.                                                                                                |

### <a name="fiscal-document"></a>Nota fiscal

Texto padrão de instalação, e tipos de produto e do documento, das notas fiscais que são emitidas e recebidas na entidade legal brasil.

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
<td><strong>Primary method of payment</strong></td>
<td>Selecione <strong>Duplicados</strong><strong>Nota promissória</strong>, ou <strong>Outro</strong> um método de pagamento principal para compras. Se você selecionar <strong>Outro</strong> neste campo, <strong>Descrição</strong> no campo, insira uma descrição do método de pagamento principal para compras.</td>
</tr>
<tr class="even">
<td><strong>Enviar sms ID</strong> ( <strong>Texto de SUFRAMA para a nota fiscal de saída</strong> O grupo de campos)</td>
<td>Selecione o ID fiscal de texto padrão do documento que é impressa em notas fiscais que são emitidas para os clientes de região do Superintendência da Zona Franca de Manaus (SUFRAMA).</td>
</tr>
<tr class="odd">
<td><strong>Enviar sms ID</strong> ( <strong>Texto de retenção de imposto para a nota fiscal de saída</strong> O grupo de campos)</td>
<td>Selecione o ID fiscal de texto padrão do documento da retenção impressos em notas fiscais.</td>
</tr>
<tr class="even">
<td><strong>Primary method of payment</strong></td>
<td>Selecione <strong>Duplicados</strong><strong>Nota promissória</strong>, ou <strong>Outro</strong> um método de pagamento principal para vendas. Se você selecionar <strong>Outro</strong> neste campo, <strong>Descrição</strong> no campo, insira uma descrição do método de pagamento principal para vendas.</td>
</tr>
<tr class="odd">
<td><strong>Product type</strong></td>
<td>Selecione o tipo de produto padrão dos itens usados para o consumo. Para um item que foi comprado para o consumo, é possível selecionar este produto no <strong>Tipo de produtos</strong> campo <strong>Detalhes lançados do produto</strong> na página.</td>
</tr>
<tr class="even">
<td><strong>Tipo de volume</strong><strong>Quantidade em massa</strong></td>
<td>O tipo de volume e a quantidade padrão de volume para itens em notas fiscais.</td>
</tr>
<tr class="odd">
<td><strong>Enable fix issue date</strong></td>
<td>Selecione esta opção para configurar a data de emissão de documento fiscal fixa para tipos de documento fiscal.</td>
</tr>
<tr class="even">
<td><strong>Item </strong></td>
<td>Selecione a ID de item usado para lançar notas fiscais de notas fiscais de texto livre.</td>
</tr>
<tr class="odd">
<td><strong>Service</strong></td>
<td>Selecione a ID de serviço usado para lançar notas fiscais de notas fiscais de texto livre que têm as linhas na opção for selecionada <strong>Informações fiscais</strong> na seção.</td>
</tr>
<tr class="even">
<td><strong>Document type</strong></td>
<td>Selecione a ID de tipo de documento padrão para textos do documento. Você pode selecionar um tipo de documento que não é atribuído em texto fiscal de documento anexado a um documento fiscal. <strong>Observação:</strong> Se um texto de documento fiscal for anexado a uma nota fiscal, você não pode alterar o tipo de documento.</td>
</tr>
<tr class="odd">
<td><strong>Item </strong></td>
<td>Selecione a ID de item usado para criar notas fiscais de imposto.</td>
</tr>
<tr class="even">
<td><strong>Sales tax code for PIS</strong></td>
<td>Selecione o código de impostos padrão para o Programa de Integração Social (PIS) usado para notas fiscais de imposto.</td>
</tr>
<tr class="odd">
<td><strong>Sales tax code for COFINS</strong></td>
<td>Selecione o código de impostos padrão de Contribuição para o Financiamento da Seguridade Social (COFINS) usado para notas fiscais de imposto.</td>
</tr>
<tr class="even">
<td><strong>Texto de documento fiscal fonte</strong></td>
<td>Selecione a ID da fonte de documento fiscal que é impressa em notas fiscais complementares.</td>
</tr>
<tr class="odd">
<td><strong>Line amount is based on</strong></td>
<td>Selecione se valores da linha nas notas fiscais de importação será baseada em de frete a bordo (FOB) ou carrinho, seguro, frete e (CIF).</td>
</tr>
<tr class="even">
<td><strong>Enviar sms o campo ID</strong></td>
<td>Selecione a ID de documento fiscal de texto que é impressa em notas fiscais de importação.</td>
</tr>
<tr class="odd">
<td><strong>Sales tax code for COFINS</strong></td>
<td>Selecione o código de impostos padrão para COFINS usado para notas fiscais complementares de impostos.</td>
</tr>
<tr class="even">
<td><strong>Código de impostos para o campo de PIS</strong></td>
<td>Selecione o código de impostos padrão de PIS usado para notas fiscais complementares de impostos.</td>
</tr>
<tr class="odd">
<td><strong>Unit</strong></td>
<td>Selecione a unidade padrão a ser usado em linhas do documento criadas para hora, despesa, o por conta, ou as transações de projeto do item.</td>
</tr>
<tr class="even">
<td><strong>Tax basic rate</strong></td>
<td>Indica o valor de taxa de impostos para cada regime previsões de impostos PIS e COFINS. Essa informações ajuda a identificar o regime cumulativo e o regime não cumulativo de cada transação de imposto.
<ul>
<li><strong>Valor básico do imposto de PIS regime acumulação</strong> – Insira a porcentagem de taxa de impostos.</li>
<li><strong>Valor básico do imposto de PIS regime não cumulativo</strong> – Insira a porcentagem de taxa de impostos</li>
<li><strong>Valor básico de impostos para COFINS em regime acumulação</strong> – Insira a porcentagem de taxa de impostos.</li>
<li><strong>Valor básico de impostos para COFINS em regime não cumulativo</strong> – Insira a porcentagem de taxa de impostos.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Impostos aproximados (origem)</strong></td>
<td>Indique a origem de informações para a porcentagem de imposto usado.</td>
</tr>
<tr class="even">
<td><strong>Enviar sms a ID (os impostos aproximados)</strong></td>
<td>Selecione a identificação do texto impresso em documentos do usuário final. Essas informações são exigidas por lei fiscal de transparência, ou os leus a Dinamarca Transparencia fiscal.</td>
</tr>
<tr class="odd">
<td><strong>Usuário final</strong></td>
<td>Selecione se o documento é para um usuário final.</td>
</tr>
<tr class="even">
<td><strong>Enviar sms a ID (FCI)</strong></td>
<td>Selecione a identificação do texto impresso em notas fiscais de FCI.</td>
</tr>
<tr class="odd">
<td><strong>ICMS-ST</strong></td>
<td>Selecione se a substituição tributário de ICMS para deve ser aplicada.</td>
</tr>
</tbody>
</table>

### <a name="taxation-code"></a>Código de tributação

Você pode configurar um código de tributação obrigatório para cada tipo de imposto.

### <a name="electronic-reporting"></a>Relatório eletrônico

Configure o tipo de relatório de eletrônico e mapeamento modelo relacionado usado para gerar o relatório.

| Campo             | descrição                                                                                                                                                                                                                                     |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Type**          | O tipo de relatório. ** NFeServices ** é o tipo que está disponível para gerar notas fiscais de serviço.                                                                                                                                         |
| **Model mapping** | Especifique o modelo a ser usado. O modelo para notas fiscais de serviço está disponível no armazenamento de serviços (LCS) do Microsoft Dynamics lifecycle. Podem baixar o modelo de LCS e uma configuração importar-lo relatando eletrônica de (ER). |

## <a name="accountant-information"></a>Contador de informações
Em O Brasil, especifique os detalhes do contador do relatório de impostos no arquivo de texto do SPED fiscal mensal, para que as autoridades fiscais tenham um registro de pessoa responsável pelo relatório de imposto. ** Detalhes ** de contador na página, insira as seguintes informações.

| Campo                   | descrição                                                                                                                |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------|
| ** CPF **                 | O número de CPF do contador.                                                                                |
| ** CNPJ **                | O CNPJ empresarial de contador, se uma outra empresa faz a contabilidade.                                              |
| ** CRC **                 | O número de registro de contador no contabilidade regionais, Aviso ou Regionais de Contabilidade (CRC). |
| **CRC issuer state**    | O estado em que o documento do CRC foi emitido.                                                                               |
| ** Data de vencimento do CRC ** | A data de validade do documento do CRC.                                                                                   |




