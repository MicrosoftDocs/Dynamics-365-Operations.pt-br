---
title: Configurar transporte em contêineres
description: Este tópico descreve como automatizar o transporte de cargas em contêineres no Gerenciamento de depósito.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f28be8993d5fc0a1632cf7a534808e64980c09b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977029"
---
# <a name="set-up-containerization"></a>Configurar transporte em contêineres

[!include [banner](../../includes/banner.md)]

Este tópico descreve como automatizar o transporte de cargas em contêineres no Gerenciamento de depósito. O posicionamento em contentores automatizado cria contêiner e o trabalho de separação para remessas quando uma onda é processada e linhas do trabalho pode ser dividida nas quantidades que atendam aos contêineres. Isso ajuda trabalhadores de depósito a separarem os itens diretamente no contêiner selecionado. Em comparação com o processo manual de embalagem, as tarefas como criar contêiner, atribuir itens e fechar contêiner são automatizadas pelo sistema. Este procedimento usa a empresa de demonstração USMF e é realizado por um gerente de depósito.


## <a name="set-up-a-wave-template"></a>Configurar um modelo de onda
1. No painel de navegação, vá para **Módulos > Gerenciamento de depósito > Configuração > Ondas > Modelos de onda**.
2. Selecione **Novo**.
3. No campo **Nome de modelo de onda**, digite um valor.
4. No campo **Descrição do modelo da onda**, digite um valor.
5. No campo **Local**, insira ou selecione um valor.
6. No campo **Depósito**, insira ou selecione um valor.
7. Expanda a seção **Métodos**. O painel **Métodos selecionados** lista os métodos para o tipo de modelo de onda selecionado. O modelo de onda deve incluir o método de transporte em contêiner.  
8. No campo **Código de etapa de onda**, digite um valor. Insira um código da etapa da onda para o método adicionado, que pode ser qualquer código. É possível adicionar mais de uma vez o método e atribuir códigos diferentes da etapa da onda. Para fazer isso, selecione **Repetir para este método** na página de **Métodos de processo de onda**.  
9. Selecione **Salvar**.
10. Feche a página.

## <a name="set-up-a-container-type"></a>Configure um tipo de contêiner
1. No painel de navegação, vá para **Módulos > Gerenciamento de depósito > Configuração > Contêineres > Tipos de contêiner**. Você pode definir seus contêineres na página **Tipos de contêiner**. Você pode configurar as dimensões físicas dos contêineres, incluindo o peso de tara, o peso máximo, o volume máximo, o tamanho, a largura, e a altura. Neste exemplo, nós temos três tamanhos diferentes de caixas.  
2. Selecione **Novo**.
3. No campo **Código de tipo de contêiner**, digite um valor.
4. No campo **Tara**, insira um número.
5. No campo **Peso máximo**, insira um número.
6. No campo **Volume**, insira um número.
7. No campo **Comprimento**, insira um número.
8. No campo **Largura**, insira um número.
9. No campo **Altura**, insira um número.
10. No campo **Descrição**, digite um valor.
11. Selecione **Salvar**.
13. Repita as etapas 2 a 11 mais duas vezes para criar três tipos totais de contêiner.
14. Feche a página.

## <a name="set-up-a-container-group"></a>Configurar um grupo de contêineres
1. No painel de navegação, vá para **Módulos > Gerenciamento de depósito > Configuração > Contêineres > Grupos de contêiner**.
2. No Painel de Ações, selecione **Novo**. Você pode configurar grupos lógicos de tipos de contêiner. Para cada grupo, você pode especificar a sequência na qual serão embalados os contêineres e a porcentagem de contêineres a serem preenchidos. As dimensões de tamanho do item são usadas para determinar se ele caberá em um contêiner. O contêiner que é o mais próximo às dimensões de tamanho do item será usado. Se você tiver vários tipos de contêiner em um grupo, recomendamos que você organize a sequência pelo tamanho, de forma o contêiner maior é o primeiro, número 1 na sequência, e o contêiner menor é o último.    
3. No campo **ID do grupo de contêineres** , digite um valor que você criou anteriormente.
4. No campo **Descrição**, digite um valor.
5. Repita as etapas 2 a 4 para todos os três tipos de contêiner criados anteriormente.
6. Selecione **Salvar**.
7. Feche a página.

## <a name="set-up-a-container-build-template"></a>Configurar um modelo de criação de contêiner
1. No painel de navegação, vá para **Módulos > Gerenciamento de depósito > Configuração > Contêineres > Modelos de criação de contêiner**.
2. Selecione **Novo**. O modelo de um edifício de contêiner é baseado no posicionamento dos processos em contentores executados. Cada modelo de compilação de contêiner define um processo de etiquetagem em contentores que será usado por um modelo da onda. a opção **Editar consulta** permite que você defina as condições no qual o modelo selecionado será processado. Por exemplo, você pode querer executar somente a colocação em contentores para clientes específicos, produtos ou depósitos, ou você pode adicionar os intervalos correspondentes de consulta ao modelo. O campo **Código da etapa da onda** é como um modelo de compilação de contêiner que está vinculado às etapas de um modelo da onda. Quando uma onda é executada, ela determina os modelos de compilação do contêiner que são usados para iniciar a colocação em contentores. O campo Tipo de consulta base determina o que embalar e no que basear a consulta do filtro. 
3. No campo **ID do modelo de contêiner**, digite um valor.
4. No campo **ID do grupo de contêineres**, insira ou selecione um valor.
5. No campo **Código de etapa de onda**, digite um valor.
6. Marque a caixa de seleção **Permitir separações divididas**.
7. Selecione **Salvar**.
8. Selecione **Restrições de combinação de contêineres**. A quebra de mistura de lógica permite que você configure regras para empacotar linhas de alocação em contêineres. Por exemplo, se você adicionar o **campo Número de itens**, quando os itens forem atribuídos aos contêineres, um novo contêiner será criado quando houver um novo número de item. Isso evitará trabalhadores das linhas de alocações de embalagem para dois clientes diferentes no mesmo contêiner.  
9. Selecione **Novo**.
10. No campo **Tabela**, selecione uma opção.
11. No campo **Seleção de Campo**, insira ou selecione um valor.
12. Selecione **OK**.

