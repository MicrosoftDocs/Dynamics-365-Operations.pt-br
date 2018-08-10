--- 
title: "Configurar transporte em contêineres"
description: "Este procedimento descreve como automatizar o transporte de cargas em contêineres no Gerenciamento de depósito."
author: ShylaThompson
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: c5faf926071dec5d2ddc1c9e921a98ecd0754917
ms.contentlocale: pt-br
ms.lasthandoff: 11/02/2017

---
# <a name="set-up-containerization"></a>Configurar transporte em contêineres

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento descreve como automatizar o transporte de cargas em contêineres no Gerenciamento de depósito. O posicionamento em contentores automatizado cria contêiner e o trabalho de separação para remessas quando uma onda é processada e linhas do trabalho pode ser dividida nas quantidades que atendam aos contêineres. Isso ajuda trabalhadores de depósito a separarem os itens diretamente no contêiner selecionado. Em comparação com o processo manual de embalagem, as tarefas como criar contêiner, atribuir itens e fechar contêiner são automatizadas pelo sistema. Este procedimento usa a empresa de demonstração USMF e é realizado por um gerente de depósito.


## <a name="set-up-a-wave-template"></a>Configurar um modelo de onda
1. Vá para Gerenciamento de depósito > Configuração > Ondas > Modelos de ondas.
2. Clique em Novo.
3. No campo Nome de modelo de onda, digite um valor.
4. No campo Descrição do modelo da onda, digite um valor.
5. No campo Local, insira ou selecione um valor.
6. No campo Depósito, insira ou selecione um valor.
7. Expandir a seção Métodos.
    * O Painel de métodos selecionados lista os métodos para o tipo de modelo de onda selecionado. O modelo de onda deve incluir o método de transporte em contêiner.  
8. Na lista, localize e selecione o PDV desejado.
9. No campo Código de etapa de onda, digite um valor.
    * Insira um código da etapa da onda para o método adicionado, que pode ser qualquer código. É possível adicionar mais de uma vez o método e atribuir códigos diferentes da etapa da onda. Para fazer isso, selecione Repetir para este método na página de Métodos de processo de onda.  
10. Clique em Salvar.
11. Feche a página.

## <a name="set-up-a-container-type"></a>Configure um tipo de contêiner
1. Vá para Gerenciamento de depósito > Configuração > Recipientes > Tipos de recipiente.
    * Você pode definir seus contêineres na página Tipos de contêiner. Você pode configurar as dimensões físicas dos contêineres, incluindo o peso de tara, o peso máximo, o volume máximo, o tamanho, a largura, e a altura. Neste exemplo, nós temos três tamanhos diferentes de caixas.  
2. Clique em Novo.
3. No campo Código de tipo de contêiner, digite um valor.
4. No campo Tara, insira um número.
5. No campo Peso máximo, insira um número.
6. No campo Volume, insira um número.
7. No campo Comprimento, insira um número.
8. No campo Largura, insira um número.
9. No campo Altura, insira um número.
10. No campo Descrição, digite um valor.
11. Clique em Salvar.
12. Clique em Novo.
13. No campo Código de tipo de contêiner, digite um valor.
14. No campo Descrição, digite um valor.
15. No campo Tara, insira um número.
16. No campo Peso máximo, insira um número.
17. No campo Volume, insira um número.
18. No campo Comprimento, insira um número.
19. No campo Largura, insira um número.
20. No campo Altura, insira um número.
21. Clique em Salvar.
22. Clique em Novo.
23. No campo Código de tipo de contêiner, digite um valor.
24. No campo Descrição, digite um valor.
25. No campo Tara, insira um número.
26. No campo Peso máximo, insira um número.
27. No campo Volume, insira um número.
28. No campo Comprimento, insira um número.
29. No campo Largura, insira um número.
30. No campo Altura, insira um número.
31. Clique em Salvar.
32. Feche a página.

## <a name="set-up-a-container-group"></a>Configurar um grupo de contêineres
1. Vá para Gerenciamento de depósito > Configuração > Recipientes > Grupos de recipientes.
2. Clique em Novo.
    * Você pode configurar grupos lógicos de tipos de contêiner. Para cada grupo, você pode especificar a sequência na qual embalar os contêineres e a porcentagem dos contêineres a serem preenchidos. As dimensões de tamanho do item são usadas para determinar se ele caberá em um contêiner. O contêiner que é o mais próximo às dimensões de tamanho do item será usado. Se você tiver vários tipos de contêiner em um grupo, recomendamos que você organize a sequência pelo tamanho, de forma o contêiner maior é o primeiro, número 1 na sequência, e o contêiner menor é o último.    
3. No campo ID do grupo de contêiner, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Novo.
6. Na lista, marque a linha selecionada.
7. No campo Tipo de contêiner, insira ou selecione um valor.
8. Clique em Novo.
9. Na lista, marque a linha selecionada.
10. No campo Tipo de contêiner, insira ou selecione um valor.
11. Clique em Novo.
12. Na lista, marque a linha selecionada.
13. No campo Tipo de contêiner, insira ou selecione um valor.
14. Clique em Salvar.
15. Feche a página.

## <a name="set-up-a-container-build-template"></a>Configurar um modelo de criação de contêiner
1. Vá para Gerenciamento de depósito > Configuração > Recipientes > Modelos de criação de recipientes.
2. Clique em Novo.
    * O modelo de um edifício de contêiner é baseado no posicionamento dos processos em contentores executados. Cada modelo de compilação de contêiner define um processo de etiquetagem em contentores que será usado por um modelo da onda. O padrão da consulta de edição permite que você defina as condições no qual o modelo selecionado será processado. Por exemplo, você pode querer executar somente a colocação em contentores para clientes específicos, produtos ou depósitos, ou você pode adicionar os intervalos correspondentes de consulta ao modelo. O campo do código da etapa da onda é como um modelo de compilação de contêiner que está vinculado às etapas de um modelo da onda. Quando uma onda é executada, ela determina os modelos de compilação do contêiner que são usados para iniciar a colocação em contentores. O campo Tipo de consulta base determina o que embalar e no que basear a consulta do filtro.  
3. Na lista, marque a linha selecionada.
4. No campo ID do modelo de contêiner, digite um valor.
5. No campo ID do grupo de contêiner, insira ou selecione um valor.
6. No campo Código de etapa de onda, digite um valor.
7. Marque a caixa de seleção Permitir separações divididas.
8. Clique em Salvar.
9. Clique em Restrições de combinação de contêineres.
    * A quebra de mistura de lógica permite que você configure regras para empacotar linhas de alocação em contêineres. Por exemplo, se você adicionar o campo Número de itens, quando os itens forem atribuídos aos contêineres, um novo contêiner será criado quando houver um novo número de item. Isso evitará trabalhadores das linhas de alocações de embalagem para dois clientes diferentes no mesmo contêiner.  
10. Clique em Novo.
11. No campo Tabela, selecione uma opção.
12. No campo Selecionar campo, insira ou selecione um valor.
13. Clique em OK.


