---
title: Configurar livros fiscais
description: Este artigo explica como configurar eventos SPED-Reinf usando Livros fiscais no Microsoft Dynamics 365 Finance para o Brasil.
author: AdamTrukawka
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8.0999999999999996
ms.search.form: ''
ms.openlocfilehash: 5a36d4da4c68ba0b3e5ae2d4edd2cfce81faf93b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279216"
---
# <a name="set-up-fiscal-books"></a>Configurar livros fiscais

Este artigo explica como configurar o módulo **Livros fiscais** para gerar e emitir eventos para as autoridades fiscais. 

## <a name="set-up-service-types"></a>Configurar tipos de serviço

A tabela de tipo de serviço representa a tabela 06. As autoridades fiscais estabeleceram esta tabela para classificar os serviços que são fornecidos, com base na atribuição de trabalho. É possível consultar uma lista detalhada dos valores disponíveis no site do sistema de registros digitais públicos (SPED).

1. Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Tipos de serviço**.
2. Selecione **Novo**.
3. Insira um código de classificação que foi estabelecido pelas autoridades fiscais e digite uma descrição.

    ![Página Tipos de serviço.](media/bra-service-type-setup.png)

4. Depois que a lista de tipos de serviço for criada, eles devem ser atribuídos a códigos de serviço. Acesse **Gerenciamento de inventário** \> **Configuração** \> **Informações fiscais** \> **Código de serviço**, e então, para cada serviço, atribua o tipo de serviço relacionado.

## <a name="set-up-tax-classification-codes"></a>Configurar códigos de classificação de imposto

1. Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Códigos de classificação fiscal**.
2. Insira os tipos de classificação disponíveis.

![Página Códigos de classificação fiscal.](media/bra-tax-classification-codes.png)

Essas informações são atribuídas à organização fiscal e podem ser encontradas na FastTab **Geral** da página **Organização fiscal**, (**Livros fiscais \> Configuração \> Organização fiscal**).

![Página Organização fiscal.](media/bra-fiscal-organization-setup.png)

## <a name="set-up-codes-explanation-suspension"></a>Configurar suspensão da explicação de códigos

1. Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Suspensão de explicação dos códigos**.
2. Configure os códigos que são usados no evento R-1070 quando a suspensão de retenção for aplicável. Esses códigos são atribuídos na página **Processo administrativo e judicial** (**Livros fiscais** \> **Periódico** \> **SPED Reinf** \> **Processo administrativo e judicial**).

![Página Suspensão de explicação dos códigos.](media/bra-codes-explanation-suspension.png)

## <a name="set-up-acquisition-type-determination"></a>Configurar a determinação do tipo de aquisição

Esta configuração é usada para determinar o tipo de aquisição agrícola dos documentos fiscais recebidos que são relatados na marca **indAquis** para o evento R-2055. 

1. Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Aquisição de produção rural**.
2. Define a classificação dos documentos fiscais, com base nos seguintes critérios:

    - **Conta do fornecedor:** Todos, grupo ou tabela
    - **CFOP:** Todos, grupo ou tabela
    - **Classificação fiscal**

## <a name="set-up-gilrat-and-senar-taxes"></a>Configurar impostos GILRAT e SENAR

**GILRAT**: a contribuição fiscal do grau de incidência de Deficiência de trabalho resultante de riscos ambientas da profissão.
**SENAR**: a contribuição fiscal relacionada à produção rural.

1. Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Códigos do imposto GILRAT** ou **Códigos do imposto SENAR**.
2. Identifique os códigos de imposto de vendas que são usados para representas impostos GILRAT e SENAR. Na definição dos códigos de imposto de vendas, o tipo de imposto deve ser definido como **Outro**. O valor desses impostos é usado nas marcas **vlrRatDescPR** e **vlrSenarDesc** para o evento R-2055.

## <a name="vendor-setup"></a>Configuração do fornecedor

- Acesse **Contas a pagar** \> **Fornecedores** \> **Todos os fornecedores**.
- Selecione um fornecedor.
- Na guia **Informações fiscais**, configure **Taxação Reinf sobre folha de pagamento**. Este novo atributo determina o tipo de taxação, pois essas informações são necessárias na marca **indOpcCP** para o evento R-2055.

## <a name="set-up-fiscal-books-parameters"></a>Configurar parâmetros dos livros fiscais

1. Acesse **Livros fiscais** > **Parâmetros das extensões de obrigações fiscais** > **SPED Reinf** > **Parâmetros SPED Reinf**.
2. Na guia **Geral**, selecione **Versão SPED Reinf**.
3. Selecione o tipo de ambiente e o status da organização fiscal.
4. Acesse **Livros fiscais** > **Configuração** > **Parâmetros dos livros fiscais**.
5. Na guia **Sequências numéricas**, configure a sequência numérica para os eventos R-2010, R-2020 e R-2055.

![Guia Sequências numéricas na página Parâmetros dos livros fiscais.](media/bra-sped-fiscal-books-parameters.png)

> [!NOTE]
> Se as sequências numéricas não tiverem sido inicializadas durante a lista de verificação da configuração para a instalação de KB, você poderá gerá-las usando um assistente. Para abrir o assistente, acesse **Administração da organização** \> **Sequências numéricas** \> **Sequências numéricas** e selecione **Gerar**. Você pode configurar a sequência numérica relacionada:
>
> - **Área:** Livros fiscais
> - **Referência**: ID de evento do SPED-Reinf
