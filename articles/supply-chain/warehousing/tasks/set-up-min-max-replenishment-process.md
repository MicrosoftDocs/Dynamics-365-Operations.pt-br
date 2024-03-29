---
title: Configurar um processo de reabastecimento mínimo/máximo
description: Este procedimento mostra como configurar um novo processo de reabastecimento que usa estratégia de reabastecimento de mínimo/máximo.
author: perlynne
ms.date: 10/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventFixedLocation, InventItemIdLookupSimple, WMSLocationIdLookup, WHSLocDirTable, InventLocationIdLookup, SysQueryForm, WHSWorkTemplateTable, WHSReplenishmentTemplates, UnitOfMeasureLookup, SysQueryTableLookUp, SysQueryFieldLookUp, SysRecurrence, WHSInventFixedLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb0fbfcceece2883c32a266bcbe659211b0b56ce
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069716"
---
# <a name="set-up-a-min-max-replenishment-process"></a>Configurar um processo de reabastecimento mínimo/máximo

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como configurar um novo processo de reabastecimento que usa estratégia de reabastecimento de mínimo/máximo. Se o estoque estiver abaixo do nível mínimo, o trabalho será criado para reabastecer o local. O procedimento também mostra como usar locais de separação fixos para permitir reabastecimento se o estoque ficar abaixo do mínimo, e como habilitar o processo de reabastecimento para executar regularmente usando um trabalho em lotes. Essas tarefas normalmente seriam realizadas por um gerente do depósito. Você pode executar este procedimento na empresa de dados de demonstração de USMF usando os valores de exemplo abaixo, ou pode executá-lo em seus próprios dados. Se você estiver usando seus próprios dados, verifique se você tem um depósito que seja habilitado para os processos de Gerenciamento de depósito (WMS).


## <a name="create-a-fixed-picking-location"></a>Criar um local de separação fixo
1. Acesse **Painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Depósito >> Localizações fixas**. Esta é uma tarefa opcional para o reabastecimento mínimo/máximo, mas se você usar local fixo de separação, isso permite que o estoque seja reabastecido mesmo se estiver abaixo do nível mínimo, pois o sistema pode determinar os itens que precisam ser reabastecidos, mesmo se não for deixado.
2. Clique em **Novo**.
3. No campo **Número do item**, insira ou selecione um valor. Se você estiver usando USMF, você pode o item A0001.  
4. No campo **Local**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar site 2.  
5. No campo **Depósito**, insira ou selecione um valor. Se você estiver usando o USMF, você pode selecionar o depósito 24.  
6. No campo **Localização**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar CP-003.  
7. Feche a página.

## <a name="create-a-replenishment-location-directive"></a>Criar uma diretiva de local de reabastecimento
1. Acesse **Gerenciamento de depósito > Configuração > Diretivas de localização**. As diretivas de localização são usadas para determinar onde os itens deverão ser separados no processo de reabastecimento.
2. No campo **Tipo de ordem de serviço**, selecione "Reabastecimento".
3. No **Painel de Ação**, clique em **Novo**.
4. No campo **Nome**, digite um valor.
5. No campo **Tipo de trabalho**, selecione "Separar".
6. No campo **Local**, insira ou selecione um valor. Se você estiver usando USMF, você pode selecionar site 2.  
7. No campo **Depósito**, insira ou selecione um valor. Se você estiver usando o USMF, você pode selecionar o depósito 24.  
8. Clique em **Salvar**.
9. Na seção **Linhas** , clique em **Novo**.
10. Na lista, marque a linha selecionada.
11. No campo **Até a quantidade**, insira um número. Por exemplo, é possível definir para 9999.  
12. Marque a caixa de seleção **Permitir separações**. Se você selecionar esta opção, o processo de criação de trabalho permitirá que as quantidades de linha de trabalho sejam separadas entre diversos locais.  
13. Clique em **Salvar**.
14. Na seção **Ações de diretiva de localização**, clique em **Novo**.
15. Na lista, marque a linha selecionada.
16. No campo **Nome**, digite um valor.
17. Clique em **Salvar**.
18. No **Painel de ações**, clique em **Editar consulta**. Você pode editar essa consulta para adicionar as restrições em que o estoque pode ser selecionado no processo de reabastecimento. Por exemplo, é possível que o estoque deva ser usado somente na área em massa do depósito.
19. Clique em **OK**.
20. Feche a página.

## <a name="create-a-replenishment-work-template"></a>Criar um modelo de trabalho de reabastecimento
1. Acesse **Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho**. O modelo de trabalho é usado para orientar o sistema como o trabalho de reabastecimento mínimo/máximo deve ser criado. No mínimo, deve haver uma linha de modelo de trabalho para separar e colocar. O modelo de trabalho dirá que não é válido até que todas as informações necessárias sejam preenchidas. 
2. No campo **Tipo de ordem de serviço**, selecione "Reabastecimento".
3. No **Painel de Ação**, clique em **Novo**.
4. No campo **Modelo de trabalho**, digite um valor.
5. Clique em **Salvar**.
6. Na seção **Detalhes do modelo de trabalho**, clique em **Novo**.
7. No campo **Tipo de trabalho**, selecione "Separar".
8. No campo **ID da classe de trabalho**, insira ou selecione um valor. Esta deve ser uma classe de trabalho relacionada ao reabastecimento. Se você estiver usando USMF, selecione Reabastecer.  
9. Na seção **Detalhes do modelo de trabalho**, clique em **Novo**.
10. Na lista, marque a linha selecionada.
11. No campo **Tipo de trabalho**, selecione 'Colocar'.
12. No campo **ID da classe de trabalho**, insira ou selecione um valor.
13. Clique em **Salvar**.
14. Feche a página.

## <a name="create-a-new-replenishment-template"></a>Crie um novo modelo de reabastecimento
1. Acesse **Gerenciamento de depósito > Configuração > Reabastecimento > Modelos de reabastecimento**. O modelo de reabastecimento é usado para definir as quantidades e os itens, e o local para reabastecer.
2. No **Painel de Ação**, clique em **Novo**.
3. No campo **Modelo de reabastecimento**, digite um valor. Insira um nome para o modelo para indicar direcionamento de reabastecimento mínimo/máximo.  
4. No campo **Descrição**, digite um valor.
5. Selecione a caixa de seleção **Permitir que a demanda da onda use quantidades não reservadas**. Se você selecionar esta opção, ela permite que o reabastecimento de demanda da onda consuma as quantidades relacionadas de reabastecimento mínimo/máximo. Por exemplo, isso pode ser útil se o trabalho de reabastecimento mínimo/máximo não é processado imediatamente, para evitar trabalho de reabastecimento de demanda desnecessário para ser criado.
6. Na seção **Detalhes do modelo de reabastecimento**, clique em **Novo**.
7. No campo **Número de sequência**, insira um número.
8. No campo **Descrição**, digite um valor.
9. Na lista, marque a linha selecionada.
10. No campo **Unidade de reabastecimento**, insira ou selecione um valor. Por exemplo, selecione pcs. É uma configuração obrigatória. Permite que você especifique uma unidade de medida diferente para o trabalho de reabastecimento em comparação com a unidade especificada para os níveis de estoque mínimo e máximo nesse modelo.
11. No campo **Modelo de trabalho**, insira ou selecione um valor. Escolha o modelo de trabalho criado anteriormente.  
12. No campo **Quantidade mínima**, insira um número. Selecione a quantidade mínima que deve acionar o reabastecimento. Por exemplo, defina para 50. É possível deixar isso definido como zero, se você estiver reabastecendo uma localização fixa e a opção **Reabastecer localizações fixas vazias** for definida como "Sim". Também é recomendado que você selecione a opção **Reabastecer apenas localizações fixas** somente por motivo de desempenho.
13. No campo **Quantidade máxima**, insira um número. Por exemplo, defina para 100.  
14. No campo **Unidade**, insira ou selecione um valor. Atribua a unidade para as quantidades mínima e máxima. Por exemplo, defina para pcs.  
15. Marque a caixa de seleção **Reabastecer localizações fixas vazias**. Marque esta caixa de seleção para reabastecer as localizações fixas quando estiverem vazias. Caso contrário, somente as localizações onde há uma quantidade disponível serão reabastecidas.
16. Marque a caixa de seleção **Reabastecer apenas localizações fixas**.
17. Clique em **Selecionar produtos**. Este é o local para definir quais produtos devem ser reabastecidos. Se a opção Locais fixos de separação estiver marcada, também é preciso definir os locais nessa consulta. As consultas específicas variantes estão disponíveis assim como consultas específicas de produto.
18. Selecione a linha **Itens**.
19. No campo **Critérios**, digite um valor. Selecione os itens a serem reabastecidos nos locais fixos. Por exemplo, digite A* para selecionar todos os números de item que começam com A.
20. Clique em **Adicionar**. Adicionar a entidade de localização (a menos que já exista) para que possa limitar o trabalho de reabastecimento fixo em locais de separação em uma área específica de depósito.
21. Na lista, marque a linha selecionada.
22. Defina o campo **Tabela** como "Localizações".
23. No campo **Campo**, selecione "ID de perfil da localização".
24. No campo **Critérios**, insira ou selecione um valor.
25. Clique em **OK**.
26. Feche a página.

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a>Configure o processo de reabastecimento para executar o trabalho em lotes
1. Acesse **Gerenciamento de depósito > Reabastecimento > Reabastecimentos**. A página de reabastecimentos permite que você configure o reabastecimento para ser executado como um trabalho em lotes, ou para exigir que inicie manualmente.
2. Clique em **Filtrar**.
3. Na lista, marque a linha selecionada.
4. No campo **Critérios**, insira ou selecione um valor.
5. Clique em **OK**.
6. Expanda a seção **Executar em segundo plano**.
7. Defina a opção **Processamento de lote** como "Sim".
8. Clique em **Recorrência**.
9. Selecione a opção **Nenhuma data de término**.
10. Defina o **Padrão de recorrência**. Por exemplo, selecione Dias.  
11. Clique em **OK**.
12. Clique em **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]