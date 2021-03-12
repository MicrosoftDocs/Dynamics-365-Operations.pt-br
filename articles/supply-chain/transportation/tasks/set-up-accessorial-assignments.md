---
title: Configurar atribuições suplementares
description: Este procedimento mostra como iniciar uma atribuição suplementar.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAccessorialAssignment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28562772c52d06fbb2004bd3a01a7bfa32f58a4e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974026"
---
# <a name="set-up-accessorial-assignments"></a>Configurar atribuições suplementares

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como iniciar uma atribuição suplementar. Normalmente isso é feito por um coordenador de transporte. Antes de você usar este guia você precisa executar o guia "Instalar hub de encargos e mestres suplementares".


## <a name="set-up-accessorial-assignment"></a>Configurar Atribuição suplementar
1. Vá para Gerenciamento de transporte > Configurar > Classificação > Atribuições suplementares.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. Ative a expansão da seção Detalhes.
5. No campo Hub, clique no botão suspenso para abrir a pesquisa.
6. Na lista, selecione o Hub para o qual você criou um mestre suplementar quando executou o guia "Instalar hub de encargos e mestres suplementares". 
7. No campo ID suplementar do Hub, clique no botão suspenso para abrir a pesquisa.
8. Na lista, clique no link na linha selecionada.
9. Ative a expansão da seção Critérios.
    * Na seção Critérios, você pode escolher os critérios exatos para quando o encargo deve ser aplicado, com base nos diferentes valores oferecidos aqui.  
10. Definir a opção Sempre aplicar para Sim.
11. No campo Nível de atribuição suplementar, selecione uma opção.
12. Ative a expansão da seção Cálculos.
13. No campo Tipo de taxa suplementar, selecione 'Fixa'.
    * O Tipo de taxa suplementar determina como calcular o encargo real. Neste exemplo é um encargo fixo.  
14. No campo Taxa suplementar, insira um número.
15. Clique em Salvar.

