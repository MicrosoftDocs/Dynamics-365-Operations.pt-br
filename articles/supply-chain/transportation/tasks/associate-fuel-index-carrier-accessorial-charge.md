---
title: Associar um índice de combustível a uma transportadora como um encargo suplementar
description: Este guia mostra como criar uma atribuição suplementar, um encargo suplementar da transportadora, um mestre suplementar para sobretaxa de combustível e como associar um índice de combustível da transportadora a uma transportadora.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c91d49c2ccdc274632e3acf94b836e19dc6cdaa8
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422558"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a>Associar um índice de combustível a uma transportadora como um encargo suplementar

[!include [banner](../../includes/banner.md)]

Este guia mostra como criar uma atribuição suplementar, um encargo suplementar da transportadora, um mestre suplementar para sobretaxa de combustível e como associar um índice de combustível da transportadora a uma transportadora. Você precisa ter configurado um índice de combustível da transportadora antes de executar esse guia. Para isso, você pode usar o guia "Configurar um índice de combustível da transportadora". Essas tarefas de configuração são tipicamente feitas por um gerente de logística. Os dados demonstrativos utilizados na criação desse procedimento são do conjunto USMF.


## <a name="create-an-accessorial-master"></a>Crie um mestre suplementar
1. Vá para Gerenciamento de transporte > Configurar > Classificação > Mestres suplementares.
2. Clique em Novo.
3. No campo Mestre suplementar, digite um valor.
4. No campo Nome, digite um valor.
5. Clique em Salvar.

## <a name="create-a-carrier-accessorial-charge"></a>Crie um encargo suplementar da transportadora
1. Vá para Gerenciamento de transporte > Configurar > Classificação > Encargos suplementares da transportadora.
2. Clique em Novo.
3. No campo ID suplementar da transportadora, digite um valor.
4. No campo Transportadora, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione o PDV desejado.
    * Neste exemplo, escolha Transportadora Rodoviária.  
6. Na lista, clique no link na linha selecionada.
7. No campo Serviço da transportadora, clique no botão suspenso para abrir a pesquisa.
8. Na lista, clique no link na linha selecionada.
9. No campo Mestre suplementar, clique no botão suspenso para abrir a pesquisa.
10. Na lista, localize e selecione o PDV desejado.
    * Neste exemplo, escolha o Mestre suplementar criado recentemente.  
11. Clique em Salvar.

## <a name="create-an-accessorial-assignment"></a>Crie uma atribuição suplementar
1. Clique em Atribuições suplementares.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. Ative a expansão da seção Critérios.
    * Nos critérios, você pode optar por sempre aplicar a sobretaxa de combustível ou, para este exemplo, escolher que ela se aplique somente dentro de uma determinada região.  
5. No campo CEP/código postal de, digite um valor.
6. No campo CEP/código postal até, digite um valor.
7. Ative a expansão da seção Cálculos.
    * Na seção de cálculo, é possível especificar como calcular a sobretaxa de combustível. Esse cálculo depende da unidade Suplementar escolhida como base para o cálculo.  
8. No campo Tipo de taxa suplementar, selecione 'Sobretaxa de combustível'.
9. No campo Unidade suplementar, selecione 'Quilometragem'.
10. No campo Região, clique no botão suspenso para abrir a pesquisa.
11. Na lista, clique no link na linha selecionada.
12. Clique em Salvar.

## <a name="update-the-carrier-rating-profile"></a>Atualize o perfil de classificação da transportadora
1. Vá para Gerenciamento de transporte > Configuração > Transportadoras > Transportadoras de envio.
2. Na lista, localize e selecione o PDV desejado.
3. Ative a expansão da seção Perfis de classificação.
4. Clique em Editar.
5. No campo Índice de combustível da transportadora, clique no botão suspenso para abrir a pesquisa.
6. Na lista, clique no link na linha selecionada.
7. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]