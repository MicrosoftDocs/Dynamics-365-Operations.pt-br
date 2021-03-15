---
title: Validar um fluxo de produção e versão
description: Este procedimento mostra como criar um fluxo de produção e uma primeira versão para lean manufacturing.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3cc8465fb56239f91982db15601cf87e3c00d3fd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980947"
---
# <a name="validate-a-production-flow-and-version"></a>Validar um fluxo de produção e versão

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um fluxo de produção e uma primeira versão para lean manufacturing. Pré-requisitos: nesse procedimento, os parâmetros de produção para lean manufacturing e as unidades de medida para tempo de classe devem ser definidos. Você também pode definir um fluxo de valor e um perfil de produção. Consulte os white papers sobre Lean manufacturing para se familiarizar com os conceitos de atividades e fluxos de produção. Este procedimento refere-se à entidade legal USMF nos dados de demonstração. No entanto, ao assumir que a entidade legal está configurada para lean manufacturing, outras entidades legais podem ser usadas.


## <a name="create-a-production-flow"></a>Criar um fluxo de produção
1. Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Nome, clique no botão suspenso para abrir a pesquisa.
6. Na lista, clique no link na linha selecionada.
    * O fluxo de valor é uma unidade operacional que abrange todos os fluxos e atividades do fluxo de valor.   Nessa fase, as unidades operacionais se limitam a uma entidade legal e não apresentam funcionalidade adicional.  
7. No campo Perfil de produção, clique no botão suspenso para abrir a pesquisa.
8. Na lista, clique no link na linha selecionada.
    * Perfis de produção permitem a definição de material, trabalho e contas WIP para um processo de produção. Para associar o contexto de contabilidade a um fluxo de produção, um perfil de produção deve ser selecionado.  
9. Clique em Salvar.

## <a name="create-a-production-flow-version"></a>Criar uma versão de fluxo de produção
1. Clique em Adicionar.
2. No campo Data de vencimento, insira uma data e hora.
    * Você pode atualizar a data de vencimento da versão a qualquer momento, mesmo a de versões ativas. Use o vencimento da versão para planejar a retirada gradual de uma versão.  
3. Clique em OK.
4. Na lista, marque a linha selecionada.
5. No campo Unidade, digite um valor.
6. Selecione a unidade Takt.
7. No campo Takt time médio, insira um número.
    * Para o controle de takt da versão do fluxo de produção, defina um takt time médio de destino.   O takt é definido como quantidade por período de tempo.  No exemplo apresentado, o takt time é 0,2 horas por 10 unidades. Para um tempo de trabalho de 8 horas, isso corresponde a uma capacidade de produtividade diária de 400 unidades.  
8. No campo Quantidade por ciclo, insira um número.
9. Expanda ou recolha a seção Detalhes da versão.
10. No campo Takt time mínimo, insira um número.
    * O takt time mínimo deve ser menor que ou igual ao takt time médio.  
11. No campo Takt time máximo, insira um número.
    * O takt time máximo deve ser maior que ou igual ao takt time médio.  
12. Inserir um número de dias no Período para tempo de ciclo real
    * O período para tempo de ciclo real é o número de dias em que os trabalhos são agregados do minuto real regressivamente para calcular o tempo de ciclo real. O valor pode ser alterado a qualquer momento e só é usado para o cálculo dos tempos de ciclo reais.  
13. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]