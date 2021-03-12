---
title: Calendários fiscais, anos fiscais e períodos
description: Este artigo discute calendários fiscais, períodos fiscais e anos e como utilizá-los para a pessoa jurídica, ativos fixos e o orçamento.
author: aprilolson
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FiscalCalendars
audience: Application User
ms.reviewer: roschlom
ms.custom: 25851
ms.assetid: a968a5e5-585e-4389-aa4e-c885a7e23413
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f40dc7227d8ee9ccc45336e9b8968937ef5f6092
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995331"
---
# <a name="fiscal-calendars-fiscal-years-and-periods"></a>Calendários fiscais, anos fiscais e períodos

[!include [banner](../includes/banner.md)]

Este artigo discute calendários fiscais, períodos fiscais e anos e como utilizá-los para a pessoa jurídica, ativos fixos e o orçamento.

Os calendários fiscais fornecem uma estrutura para a atividade financeira de uma organização. Cada calendário fiscal contém um ou mais anos fiscais, e cada ano fiscal contém vários períodos. Os calendários fiscais podem ser baseados no ano calendário de 1º de janeiro a 31 de dezembro, ou qualquer data selecionada. Por exemplo, algumas organizações selecionam um calendário fiscal que começa em 1º de julho de um ano e termina em 30 de junho do ano seguinte. 

Não há limite para o número de calendários fiscais que você pode criar, e nenhum limite para o número de anos fiscais que pode ser criados para um calendário fiscal. Cada calendário fiscal é independente de sua organização, e pode ser usado por várias entidade legais na organização. Por exemplo, uma organização tem oito departamentos e cada departamento é uma entidade legal independente. Cinco deles compartilham o mesmo calendário fiscal e três usam calendários fiscais diferentes. Você pode criar um calendário fiscal para as cinco entidades legais que compartilham o mesmo calendário fiscal e depois criar calendários fiscais diferentes para as outras entidades legais.

## <a name="create-fiscal-calendars-fiscal-years-and-periods"></a>Criar calendários fiscais, anos fiscais e períodos
É possível criar e excluir calendários fiscais, anos fiscais e períodos na página Calendários fiscais. Você também pode dividir períodos existentes e criar os períodos de fechamento que podem ser usados para fechar um ano fiscal. 

Um período de fechamento é usado para separar as transações da contabilidade que são geradas quando um ano fiscal é fechado. Quando as transações de fechamento fazem parte de um período fiscal, será mais fácil criar demonstrativos financeiros que inclua ou exclua tipos diferentes de lançamentos de fechamento. Se um ano fiscal for dividido por 12 períodos fiscais, o período de fechamento geralmente será o 13º período. No entanto, um período de fechamento pode ser criado a partir de qualquer período que tenha um status Aberto. 

Ao criar um período de fechamento, selecione um período que tenha um status Aberto e com as datas que deseja usar. O novo período de fechamento copiará as datas inicial e final do período existente. O período original continuará a existir. Por exemplo, você seleciona p Período 12, que é o último período no ano fiscal e que tem datas de 1º de agosto a 31 de agosto. Você digita um nome para o período de fechamento, como Fechamento. Depois de criar o novo período de fechamento, você terá o período original e o período de fechamento. Os dois têm as datas que iniciam em 1º de agosto e terminam em 31 de agosto.

## <a name="select-fiscal-calendars-for-ledgers-fixed-assets-and-budget-cycles"></a>Selecionar calendários fiscais para razões, ativos fixos e ciclos orçamentários
Os calendários fiscais são usados com depreciação de ativo fixo, transações financeiras e ciclos orçamentários. Quando você cria um calendário fiscal, você pode usá-lo para várias finalidades. Você pode selecionar um calendário fiscal para um registro de ativo fixo para torná-lo um calendário de ativos fixos. Você pode selecionar um calendário fiscal para um razão para torná-lo um calendário do razão. E você pode selecionar um calendário fiscal para um ciclo orçamentário para torná-lo um calendário de orçamento. Você pode usar o mesmo calendário fiscal para todos eles.

### <a name="select-a-fiscal-calendar-for-your-legal-entity"></a>Selecionar um calendário fiscal para sua entidade legal

Selecione o calendário fiscal que você deseja usar para o razão de sua entidade legal no formulário Razão. Um calendário fiscal deve ser selecionado na página Razão para cada entidade legal. Depois que um calendário fiscal é marcado, será possível configurar o status do período e as permissões na página Calendário do razão para todos os períodos que fazem parte de um ano fiscal.

### <a name="select-a-fiscal-calendar-for-fixed-assets"></a>Selecionar um calendário fiscal para ativos fixos

Você pode selecionar um calendário fiscal para um registro de ativo fixo, e esse calendário fiscal será usado pelos ativos fixos que usam o registro selecionado. Você pode selecionar qualquer calendário fiscal que esteja definido na página Calendários fiscais.

### <a name="define-budget-cycle-time-spans"></a>Definir períodos de tempo do ciclo orçamentário

Os ciclos orçamentários são o período durante o qual um orçamento é usado. Os ciclos orçamentários podem incluir parte de um ano fiscal ou vários anos fiscais, como um ciclo orçamentário bienal de dois anos ou um ciclo orçamentário trienal de três anos. O período de tempo do ciclo orçamentário define o número de períodos incluídos no ciclo orçamentário. Para especificar o período de tempo do ciclo orçamentário, use a página Períodos de tempo do ciclo orçamentário.

## <a name="maintain-periods-for-your-organization"></a>Manter períodos para sua organização
Você pode usar a página Calendário do razão para exibir os detalhes do calendário fiscal, anos fiscais e períodos usados por sua organização. Você também pode alterar o status dos períodos e selecionar quais usuários podem lançar transações contábeis em períodos. Por exemplo, no início de um novo período, você pode querer que um grupo de usuários conclua o lançamento de transações financeiras do período anterior, enquanto outros grupos trabalhem apenas no novo período.





