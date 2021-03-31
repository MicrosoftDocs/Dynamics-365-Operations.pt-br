---
title: Definir agendas de continuidade
description: Este tópico aborda a configuração de um programa de continuidade (também conhecido como pedidos recorrentes).
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f385d97ce8c458ada944609e165ebd0db500b546
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229927"
---
# <a name="define-continuity-schedules"></a>Definir agendas de continuidade

[!include [banner](../includes/banner.md)]

Este tópico aborda a configuração de um programa de continuidade (também conhecido como pedidos recorrentes). Este tópico usa a empresa USRT nos dados de demonstração.


## <a name="create-continuity-program"></a>Criar programa de continuidade
1. Vá para Varejo e Comércio > Continuidade > Programas de continuidade.
2. Clique em Novo.
3. No campo ID da Agenda, digite a ID da agenda de continuidade.
4. No campo Início da ordem, selecione "Primeiro evento".
    * Se um cliente estabelecer uma nova ordem para o programa da continuidade, há duas opções para envio do produto: 1. Primeiro evento: o primeiro produto no programa de continuidade será enviado.  2. Evento atual: o produto atual será enviado. Por exemplo. três meses no programa, o cliente receberá o terceiro no programa.  
5. Selecione "Sim" para solicitar a data inicial da ordem.
6. Clique em Adicionar linha.
7. No campo Número do item, digite o número de item do primeiro produto ("0013").
8. Digite "CP".
9. Insira a dada em que o primeiro produto estará disponível para ordem.
10. Clique em Adicionar nova linha.
11. No campo do número de item, digite '0014'.
12. No campo Código do intervalo de datas, apague o valor para que o campo fique vazio.
    * Nesse procedimento, desmarque o intervalo de datas. Você verá a data como incremental a partir da data inicial do primeiro item.  
13. Aqui você inserirá o intervalo no qual os produtos serão enviados. Digite "30".
    * Para um programa mensal, você inserirá 30 dias para o intervalo.  
14. Clique em Adicionar linha.
15. No campo do número de item, digite '0015'.
16. Digite "Fim".
17. Clique em Salvar.

## <a name="assign-to-continuity-item"></a>Atribuir ao item de continuidade
1. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
2. Selecione o item "0016".
    * Nesse procedimento, você selecionará o item nº 0016. Geralmente, você terá criado um produto liberado com lógica comercial de continuidade adicional aplicada ao ser colocada em uma ordem de venda em call center.  
3. Na lista, clique no link na linha selecionada.
4. Clique em Editar.
5. Expanda ou recolha a seção Venda.
6. Aqui você inserirá o programa de continuidade que esse item representa. Digite a ID da agenda criada anteriormente.
    * Quando esse item é vendido em um call center, a lógica comercial adicional é aplicada a partir do programa de continuidade selecionado.  
7. Clique em Salvar.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]