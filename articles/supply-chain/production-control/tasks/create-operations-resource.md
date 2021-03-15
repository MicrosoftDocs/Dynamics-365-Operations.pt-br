---
title: Criar um recurso de operações
description: Um recurso de operações executa as atividades de um projeto ou um processo de produção.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b91d5ea7618010ab9d4006d643c59a7f995eb0c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981222"
---
# <a name="create-an-operations-resource"></a>Criar um recurso de operações

[!include [banner](../../includes/banner.md)]

Um recurso de operações executa as atividades de um projeto ou um processo de produção. Estes procedimentos mostram como definir um recurso de operações. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.

1. Vá para Recursos.
2. Clique em Novo.
3. No campo Recurso, digite um valor.
4. No campo Descrição, digite um valor.

## <a name="define-capacity-and-consumption-parameters"></a>Definir os parâmetros de capacidade e de consumo
1. Expandir a seção Operação.
2. No campo de porcentagem de Sucata, insira um número.
3. No campo categoria de Configuração, insira ou selecione um valor.
    * Especifique a categoria de custo que define como contabilizar os custos de configuração.  
4. No campo categoria de Tempo de execução, insira ou selecione um valor.
    * Especifique a categoria de custo que define como contabilizar os custos de tempo de execução.  
5. No campo categoria de Quantidade, insira ou selecione um valor.
    * Especifique a categoria de custo que define como contabilizar os custos do recurso com base na quantidade de saída.  
6. No campo Unidade de capacidade, selecione uma opção.
    * Especifique a unidade na qual expressar a capacidade do recurso de operações.  
7. No campo Capacidade, insira um número.
8. No campo Porcentagem de eficiência, insira um número.
    * Especifique a eficiência que você espera do recurso de operações. A porcentagem de eficiência ajusta a produtividade do recurso de operações e afeta o tempo que é reservado para o recurso.  
9. No campo percentual do plano de Operações, insira um número.
    * Especifique a porcentagem máxima de capacidade do recurso de operações que você deseja usar no plano de operações.  
10. Selecione Sim no campo da capacidade finita.
    * Definir esta opção como Sim se o recurso de operações for planejado com base na capacidade real disponível e se as reservas de capacidade existentes forem consideradas. Se essa opção estiver definida como Não, o recurso de operações é considerado para que a capacidade infinita e o recurso possam ser reservados.  
11. Selecione Sim no campo Recurso de afunilamento.

## <a name="define-working-times"></a>Definir horários de trabalho
1. Expandir a seção Calendários.
2. Clique em Adicionar.
3. No campo Calendário, insira ou selecione um valor.
    * Especifique o calendário de produção que define a capacidade (em horas) do recurso.  
4. Na lista, localize e selecione o PDV desejado.
5. Na lista, clique no link na linha selecionada.

## <a name="define-resource-capabilities"></a>Definir capacidades do recurso
1. Expandir a seção Capacidades.
2. Clique em Adicionar.
    * Um recurso é a capacidade de um recurso de operações de executar uma atividade específica. O mecanismo de planejamento aloca recursos correspondentes as requisições de recurso de cada atividade à capacidades dos recursos de operações disponíveis.  
3. No campo Capacidade, insira ou selecione um valor.
4. No campo Nível, insira um número.
    * Especifique o nível de proficiência para que o recurso processe a capacidade.  
5. No campo Prioridade, insira um número.
    * Especifique a prioridade do recurso de operações em relação à capacidade. Ao planejar prioridade, o recurso de operações com prioridade mais alta (o menor valor numérico) é selecionado pela primeira vez.  

## <a name="assign-resource-to-resource-group"></a>Atribuir um recurso ao grupo de recursos
1. Expandir a seção Grupo de de recursos.
2. Clique em Adicionar.
    * O grupo de recursos define o site, a unidade de produção e o contexto de depósito para recursos de operações. O recurso de operações só pode ser planejado quando atribuído a um grupo de recursos, e apenas o local no qual o grupo de recursos está localizado.  
3. No campo Grupo de recurso, insira ou selecione um valor.
4. No campo Local de entrada, insira ou selecione um valor.
    * Especifique o local no depósito de onde o recurso de operações está consumindo materiais.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]