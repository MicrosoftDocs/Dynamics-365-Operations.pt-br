--- 
title: "Configurar um processo de reabastecimento mínimo/máximo"
description: "Este procedimento mostra como configurar um novo processo de reabastecimento que usa estratégia de reabastecimento de mínimo/máximo."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: 4d591eec163cfe2952f37b93e634eae676860889
ms.contentlocale: pt-br
ms.lasthandoff: 11/02/2017

---
# <a name="set-up-a-min-max-replenishment-process"></a>Configurar um processo de reabastecimento mínimo/máximo

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar um novo processo de reabastecimento que usa estratégia de reabastecimento de mínimo/máximo. Se o estoque estiver abaixo do nível mínimo, o trabalho será criado para reabastecer o local. O procedimento também mostra como usar locais de separação fixos para permitir reabastecimento se o estoque ficar abaixo do mínimo, e como habilitar o processo de reabastecimento para executar regularmente usando um trabalho em lotes. Essas tarefas normalmente seriam realizadas por um gerente do depósito. Você pode executar este procedimento na empresa de dados de demonstração de USMF usando os valores das notas exemplo, ou pode executá-la em seus próprios dados. Se você estiver usando seus próprios dados, verifique se você tem um depósito que seja habilitado para os processos de gerenciamento de depósito.


## <a name="create-a-fixed-picking-location"></a>Criar um local de separação fixo
1. Vá para Gerenciamento de depósito > Configuração > Depósito > Locais fixos.
    * Esta é uma tarefa opcional para o reabastecimento mínimo/máximo, mas se você usar local fixo de separação, isso permite que o estoque seja reabastecido mesmo se estiver abaixo do nível mínimo, pois o sistema pode determinar os itens que precisam ser reabastecidos, mesmo se não for deixado.  
2. Clique em Novo.
3. No campo Número do item, insira ou selecione um valor.
    * Se você estiver usando USMF, é possível selecionar o item A0001.  
4. No campo Local, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar site 2.  
5. No campo Depósito, insira ou selecione um valor.
    * Se você estiver usando o USMF, você pode selecionar o depósito 24.  
6. No campo Localização, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar CP-003.  
7. Feche a página.

## <a name="create-a-replenishment-location-directive"></a>Criar uma diretiva de local de reabastecimento
1. Vá para Gerenciamento de depósito > Configuração > Diretivas de local.
    * As diretivas de localização são usadas para determinar onde os itens deverão ser separados no processo de reabastecimento.  
2. No campo Tipo de ordem de trabalho, selecione "Reabastecimento".
3. Clique em Novo.
4. No campo Nome, digite um valor.
5. No campo Tipo de trabalho, selecione 'Separar'.
6. No campo Local, insira ou selecione um valor.
    * Se você estiver usando USMF, você pode selecionar site 2.  
7. No campo Depósito, insira ou selecione um valor.
    * Se você estiver usando o USMF, você pode selecionar o depósito 24.  
8. Clique em Salvar.
9. Clique em Novo.
10. Na lista, marque a linha selecionada.
11. No campo Até a quantidade, insira um número.
    * Por exemplo, é possível definir para 9999.  
12. Marque a caixa de seleção Permitir separações.
    * Se você selecionar esta opção, o processo de criação de trabalho permitirá que as quantidades de linha de trabalho sejam separadas entre diversos locais.  
13. Clique em Salvar.
14. Clique em Novo.
15. Na lista, marque a linha selecionada.
16. No campo Nome, digite um valor.
17. Clique em Salvar.
18. Clique em Editar consulta.
    * Você pode editar essa consulta para adicionar as restrições em que o estoque pode ser selecionado no processo de reabastecimento. Por exemplo, é possível que o estoque deva ser usado somente na área em massa do depósito.  
19. Clique em OK.
20. Feche a página.

## <a name="create-a-replenishment-work-template"></a>Criar um modelo de trabalho de reabastecimento
1. Vá para Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho.
    * O modelo de trabalho é usado para orientar o sistema como o trabalho de reabastecimento mínimo/máximo deve ser criado. No mínimo, deve haver uma linha de modelo de trabalho para separar e colocar. O modelo de trabalho dirá que não é válido até que todas as informações necessárias sejam preenchidas.  
2. No campo Tipo de ordem de trabalho, selecione "Reabastecimento".
3. Clique em Novo.
4. No campo Modelo de trabalho, digite um valor.
5. Clique em Salvar.
6. Clique em Novo.
7. No campo Tipo de trabalho, selecione 'Separar'.
8. No campo ID de classe de trabalho, insira ou selecione um valor.
    * Esta deve ser uma classe de trabalho relacionada ao reabastecimento. Se você estiver usando USMF, selecione Reabastecer.  
9. Clique em Novo.
10. Na lista, marque a linha selecionada.
11. No campo Tipo de trabalho, selecione 'Colocar'.
12. No campo ID de classe de trabalho, insira ou selecione um valor.
13. Clique em Salvar.
14. Feche a página.

## <a name="create-a-new-replenishment-template"></a>Crie um novo modelo de reabastecimento
1. Vá para Gerenciamento de depósito > Configuração > Reabastecimento > Modelos de reabastecimento.
    * O modelo de reabastecimento é usado para definir as quantidades e os itens, e o local para reabastecer.  
2. Clique em Novo.
3. No campo Modelo de reabastecimento, digite um valor.
    * Insira um nome para o modelo para indicar direcionamento de reabastecimento mínimo/máximo.  
4. No campo Descrição, digite um valor.
5. Selecione a caixa de seleção Permitir que a demanda da onda use quantidades não reservadas.
    * Se você selecionar esta opção, ela permite que o reabastecimento de demanda da onda consuma as quantidades relacionadas de reabastecimento mínimo/máximo. Por exemplo, isso pode ser útil se o trabalho de reabastecimento mínimo/máximo não é processado imediatamente, para evitar trabalho de reabastecimento de demanda desnecessário para ser criado.  
6. Clique em Novo.
7. No campo de número de sequência, insira um número.
8. No campo Descrição, digite um valor.
9. Na lista, marque a linha selecionada.
10. No campo Unidade de reabastecimento, insira ou selecione um valor.
    * Por exemplo, selecione pcs. É uma configuração obrigatória. Permite que você especifique uma unidade de medida diferente para o trabalho de reabastecimento em comparação com a unidade especificada para os níveis de estoque mínimo e máximo nesse modelo.  
11. No campo Modelo de trabalho, insira ou selecione um valor.
    * Escolha o modelo de trabalho criado anteriormente.  
12. No campo Quantidade mínima, insira um número.
    * Selecione a quantidade mínima que deve acionar o reabastecimento. Por exemplo, defina para 50. É possível deixar isso definido como zero, se você estiver reabastecendo um local fixo e a opção fixa em branco entre os locais de reabastecimento for definida como Sim. Também é recomendado que você selecione a opção fixa entre os locais de reabastecimento somente por motivo de desempenho.  
13. No campo Quantidade máxima, insira um número.
    * Por exemplo, defina para 100.  
14. No campo Unidade, insira ou selecione um valor.
    * Atribua a unidade para as quantidades mínima e máxima. Por exemplo, defina para pcs.  
15. Marque a caixa de seleção Reabastecer localizações fixas vazias.
    * Marque esta caixa de seleção para reabastecer as localizações fixas quando estiverem vazias. Caso contrário, somente as localizações onde há uma quantidade disponível serão reabastecidas.  
16. Marque a caixa de seleção Reabastecer apenas localizações fixas.
17. Clique em Selecionar produtos.
    * Este é o local para definir quais produtos devem ser reabastecidos. Se a opção Locais fixos de separação estiver marcada, também é preciso definir os locais nessa consulta. As consultas específicas variantes estão disponíveis assim como consultas específicas de produto.  
18. Selecione a Linha de itens.
19. No campo Critérios, digite um valor.
    * Selecione os itens a serem reabastecidos nos locais fixos. Por exemplo, digite A* para selecionar todos os números de item que começam com A.  
20. Clique em Adicionar.
    * Adicionar a entidade de localização (a menos que já exista) para que possa limitar o trabalho de reabastecimento fixo em locais de separação em uma área específica de depósito.  
21. Na lista, marque a linha selecionada.
22. Defina o campo Tabela para Locais.
23. No campo Campo, selecione ID de perfil de local.
24. No campo Critérios, insira ou selecione um valor.
25. Clique em OK.
26. Feche a página.

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a>Configure o processo de reabastecimento para executar o trabalho em lotes
1. Vá para Gerenciamento de depósito > Reabastecimento > Reabastecimentos.
    * A página de reabastecimentos permite que você configure o reabastecimento para ser executado como um trabalho em lotes, ou para exigir que inicie manualmente.  
2. Clique em Filtro.
3. Na lista, marque a linha selecionada.
4. No campo Critérios, insira ou selecione um valor.
5. Clique em OK.
6. Expanda a seção Executar em segundo plano.
7. Defina a opção Processamento de lote para Sim.
8. Clique em Recorrência.
9. Selecione a opção Nenhuma data de término.
10. Defina o padrão de Recorrência.
    * Por exemplo, selecione Dias.  
11. Clique em OK.
12. Clique em OK.


