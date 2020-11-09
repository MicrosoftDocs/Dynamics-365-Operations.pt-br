---
title: Configurar livros fiscais
description: Este tópico explica como configurar livros fiscais. Eles ajudam a consolidar livros fiscais e estatutários em arquivos eletrônicos para que você possa atender aos requisitos do SPED.
author: v-gonode
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FBTaxStatement_BR
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: aff53d8ab85263d425cc207aff03f2836c7ccfda
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015023"
---
# <a name="configure-fiscal-books"></a>Configurar livros fiscais

[!include [banner](../includes/banner.md)]

Os livros fiscais ajudam a criar a apuração de imposto do estabelecimento fiscal, o pagamento de imposto e o relatório de imposto por meio do Sistema Público de Escrituração Digital (SPED). Os arquivos do SPED fornecem informações detalhadas sobre as apurações e pagamentos de imposto em transações com mercadorias, ativos fixos e serviços, bem como em transações na contabilidade. 

## <a name="set-up-requirements-for-sped-fiscal-text-files"></a>Configurar requisitos para arquivos de texto fiscais SPED

> [!NOTE]
> Antes de configurar seu arquivo de texto fiscal do SPED, é preciso importar o modelo de dados **Modelo do SPED** e a configuração de arquivo **EFD ICMS IPI - nnn (BR)** no módulo **Relatório eletrônico**. No Relatório eletrônico, é possível baixar o modelo e a configuração de arquivo do repositório publicado pela Microsoft. Como alternativa, você pode obter uma versão atualizada do Microsoft Dynamics Lifecycle Services (LCS).

1. Na página **Parâmetros das extensões de obrigações fiscais** , clique em **Novo na geração eletrônica de relatórios**.
2. Insira um nome para a obrigação fiscal.
3. Selecione **Modelo do SPED** como o nome do mapeamento de modelo e **EFD ICMS IPI - nnn (BR)** como mapeamento do formato.

## <a name="set-up-requirements-for-gia-text-files"></a>Configurar requisitos para arquivos de texto GIA

> [!NOTE]
> Antes de configurar seu arquivo de texto do Guia de Informação e Apuração (GIA), é preciso importar o modelo de dados **Modelo do SPED** e a configuração de arquivo **GIA** no Relatório eletrônico. No Relatório eletrônico, é possível baixar o modelo e a configuração de arquivo do repositório publicado pela Microsoft. Como alternativa, é possível obter uma versão atualizada do LCS.

1. Na página **Parâmetros das extensões de obrigações fiscais** , clique em **Novo na geração eletrônica de relatórios**.
2. Insira um nome para a obrigação fiscal.
3. Selecione **Modelo do SPED** como o nome do mapeamento de modelo e **GIA** como mapeamento do formato.

## <a name="set-up-requirements-for-gia-st-text-files"></a>Configurar requisitos para arquivos de texto GIA-ST

> [!NOTE]
> Antes de configurar seu arquivo de texto do GIA-ST, é preciso importar o modelo de dados **Modelo do SPED** e a configuração de arquivo **GIA-ST** no Relatório eletrônico. No Relatório eletrônico, é possível baixar o modelo e a configuração de arquivo do repositório publicado pela Microsoft. Como alternativa, é possível obter uma versão atualizada do LCS.

1. Na página **Parâmetros das extensões de obrigações fiscais** , clique em **Novo na geração eletrônica de relatórios**.
2. Insira um nome para a obrigação fiscal.
3. Selecione **Modelo do SPED** como o nome do mapeamento de modelo e **GIA-ST** como mapeamento do formato.

## <a name="set-up-requirements-for-sped-contributions-text-files"></a>Configurar requisitos para arquivos de texto de contribuições SPED

> [!NOTE]
> Antes de configurar seu arquivo de texto de contribuições SPED, é preciso importar o modelo de dados **Modelo do SPED** e a configuração de arquivo **EFD Contribuições - nnn (BR)** no Relatório eletrônico. No Relatório eletrônico, é possível baixar o modelo e a configuração de arquivo do repositório publicado pela Microsoft. Como alternativa, é possível obter uma versão atualizada do LCS.

1. Na página **Parâmetros das extensões de obrigações fiscais** , clique em **Novo na geração eletrônica de relatórios**.
2. Insira um nome para a obrigação fiscal.
3. Selecione **Modelo do SPED** como o nome do mapeamento de modelo e **EFD Contribuições - nnn (BR)** como mapeamento do formato.

## <a name="set-up-adjustment-codes-for-icms-taxes-on-fiscal-documents"></a>Configurar códigos de ajuste para impostos ICMS em notas fiscais

1. Na página **Ajuste e informações para documentos fiscais** , no campo **Identificação** , insira um código de ajuste. Depois insira uma descrição do código de ajuste.
2. Selecione valores apropriados nos campos **Estado** , **Classificação** , **Tipo de apuração** , **Responsabilidade** , **Tipo de pagamento de imposto** e **Origem do imposto**.

    O campo **Código de ajuste** é preenchido automaticamente, com base nos valores dos outros campos na página.

3. Insira o código de ocorrência para a obrigação fiscal GIA.
4. Insira a primeira e última datas a que os códigos de ajuste se aplicam.
5. Na Guia Rápida **Pagamento** , marque a caixa de seleção **Outro débito** para criar um pagamento de ajuste de imposto adicional que não está incluído no pagamento periódico.
6. Na Guia Rápida **Lançamento** , no campo **Contas da empresa** , selecione a entidade legal na qual as transações de ajuste de impostos serão lançadas.
7. No campo **Código do imposto** , selecione o código de imposto que deve ser usado para selecionar contas a receber ou a conta de contas a pagar. A conta selecionada depende do ajuste de imposto ser um débito ou crédito. 
8. Selecione a conta principal que deve ser usada para lançar a parte da receita ou as despesas da transação de ajuste.

## <a name="set-up-adjustment-codes-for-icms-tax"></a>Configurar códigos de ajuste para o imposto de ICMS

1. Na página **Tabela de códigos de ajuste de ICMS e ICMS-ST** , no campo **Identificação** , insira um código de ajuste. Depois insira uma descrição do código de ajuste.
2. Selecione um estado.
3. Selecione o tipo de imposto: 

    - **ICMS** – O código de ajusta é usado para o imposto federal Imposto sobre Circulação de Mercadorias e Serviços (ICMS).
    - **ICMS-ST** – O código de ajuste é usado para imposto federal de ICMS-ST.
    - **ICMS-DIFF** – O código de ajuste é usado para imposto federal de ICMS-DIFF.

4. Selecione uma classificação e insira um código de ocorrência.

    O campo **Código de ajuste** é preenchido automaticamente, com base nos valores dos outros campos na página.

5. Insira a primeira e última datas a que os códigos de ajuste se aplicam.
6. No grupo do campo **GIA** , selecione um código de ocorrência.
7. Na Guia Rápida **Pagamento** , selecione a opção **Outro débito** para criar um pagamento de ajuste de imposto adicional que não está incluído no pagamento periódico.
8. Na Guia Rápida **Lançamento** , no campo **Contas da empresa** , selecione a entidade legal na qual as transações de ajuste de impostos serão lançadas.
9. No campo **Código do imposto** , selecione o código de imposto que deve ser usado para selecionar contas a receber ou a conta de contas a pagar. A conta selecionada depende do ajuste de imposto ser um débito ou crédito. 
10. Selecione a conta principal que deve ser usada para lançar a parte da receita ou as despesas da transação de ajuste.

## <a name="set-up-adjustment-codes-for-ipi-taxes"></a>Configurar códigos de ajuste para impostos IPI

1. Na página **Tabela de códigos de ajuste de IPI** , insira um código de ajuste. O primeiro caractere deve ser **0** (zero) para um ajuste de crédito ou **1** para um ajuste de débito.
2. Insira uma descrição.
3. Se o código do ajuste for usado para relatar a reversão de um valor de imposto IPI (Imposto sobre Produtos Industrializados) que foi relatado anteriormente, selecione a opção **Código de ajuste de estorno**.
4. Insira a primeira e última datas a que o código de ajuste se aplica.

Na página **Códigos de observação** , é possível configurar os códigos de observação a serem usados para ajustar os valores de ICMS ou ICMS-ST.

## <a name="set-up-fiscal-books-parameters-per-state"></a>Configurar parâmetros de livros fiscais por estado

1. Na página **Parâmetros de livros fiscais por estado** , selecione um estado.
2. Se os valores do imposto ICMS puderem ser ajustados em notas fiscais, selecione a opção **Por nota fiscal** e selecione o código de ajuste padrão e o código de observação.

    Se os valores do imposto ICMS não puderem ser ajustados em notas fiscais, selecione a opção **Por nota fiscal** e selecione o código de ajuste padrão.

3. Para calcular automaticamente uma parcela de crédito ICMS quando uma transação de saída é criada, selecione a opção **Calcular parcela para transações de saída**.

## <a name="set-up-a-fiscal-organization"></a>Configurar uma organização fiscal

1. Na página **Organização fiscal** , no campo **Estabelecimento fiscal matriz** , selecione uma organização fiscal que é usada para as contribuições SPED.
2. Na Guia Rápida **Estabelecimento fiscal** , os estabelecimentos fiscais são automaticamente adicionados à lista se tiverem o mesmo número de nove dígitos do Cadastro Nacional de Pessoas Jurídicas (CNPJ)/Cadastro de Pessoas Físicas (CPF) como a organização fiscal que você selecionou no campo **Estabelecimento fiscal matriz**. Para remover um estabelecimento fiscal adicionado à lista, clique em **Remover**. 
3. Na Guia Rápida **Contrato social da empresa** , insira a data de arquivo morto do contrato de constituição da empresa e a conversão da empresa.
4. Na Guia Rápida **SCP** , selecione o tipo de empresa Sociedade em Conta de Participação (SCP): 

    - Não participante de SCP como sócio ostensivo
    - Participante como parceiro SCP
    - SCP

5. Na Guia Rápida **SCP relacionado** , clique em **Adicionar** para inserir o nome e o código de uma empresa relacionada ao SCP. 

    > [!NOTE]
    > Essas informações estão disponíveis se você selecionou **Participante como parceiro SCP** como o tipo de empresa SCP.

6. Na Guia Rápida **Representante legal** , clique em **Adicionar** para inserir o nome do representante legal da empresa.
7. Insira o número do CPF e a função do representante legal. 
8. Na Guia Rápida **Auditores independentes** , clique em **Adicionar** para inserir o nome do auditor e o número de registro.
9. Para remover um auditor independente que foi adicionado à lista, clique em **Remover**. 

    > [!NOTE] 
    > Essa opção está disponível quando a opção **Empresa de grande porte** é selecionada.

Na página **Grupos de ativos fixos** , você pode configurar um grupo de ativos fixos.

## <a name="set-up-requirements-for-the-sped-ecd-tax-statement"></a>Configurar requisitos para a declaração de imposto SPED ECD

1. Na página **Parâmetros das extensões de obrigações fiscais** , clique em **SPED ECD**. Depois, na Guia Rápida **Parâmetros de configuração** , clique em **Abrir**.
2. Selecione a empresa para a qual gerar o arquivo de texto do SPED ECD (Escrituração Contábil Digital).
3. Selecione o conjunto de dimensões financeiras na qual o formato de arquivo de texto do SPED ECD deve se basear. O conjunto de dimensões financeiras deve incluir a conta principal e as dimensões de centro de custo.
4. Selecione o local onde o arquivo de texto do SPED ECD deve ser gerado.

    O tipo de registro é atribuído automaticamente com base no tipo da organização fiscal:
    
    - **G** – O registro é usado para todas as transações do diário do razão.
    - **S** – O registro é usado para a empresa SCP.

5. Selecione o tipo de situação de empresa ou deixe o campo em branco se ele deve representar a situação regular.
6. No campo **Período fiscal de abertura** , selecione uma das seguintes opções: **Regular** , **Abertura** , **Divisão, Fusão ou Aquisição** ou **Obrigatório**.
7. Selecione a versão de layout de arquivo do formato de arquivo de texto fiscal do SPED ECD a ser gerado. As seguintes versões de layout de arquivo para ECD são suportadas atualmente:

    - Versão 2.00 para SPED ECD até o ano fiscal 2013
    - Versão 3.00 para SPED ECD até o ano fiscal 2014
    - Versão 4.00 para SPED ECD até o ano fiscal 2015
    - Versão 5.00 para SPED ECD até o ano fiscal 2016

8. No campo **Número de inscrição do auditor** , insira o número do auditor da empresa.
9. Insira o nome do auditor.
10. Se a empresa for uma empresa de grande porte, selecione a opção **Empresa de grande porte**. 

> [!NOTE]
> Os campos para as etapas 8, 9 e 10 não estão disponíveis quando a versão 3.0 for selecionada. Essas informações foram alteradas e incluídas na configuração da organização fiscal.

Na página **Detalhes do contador** , você pode configurar informações de contador para a escrituração de imposto.
