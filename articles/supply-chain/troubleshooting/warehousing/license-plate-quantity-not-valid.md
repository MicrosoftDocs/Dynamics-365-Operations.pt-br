---
title: A quantidade não é válida ao registrar ordens de entrada
description: 'Se a quantidade alocada para uma placa de licença exceder a quantidade que ainda deve ser recebida, você receberá a mensagem de erro: "A quantidade não é válida".'
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5099b320447bf59c72f5017564ea660f19c690a5
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475620"
---
# <a name="license-plate-quantity-is-not-valid-when-registering-inbound-orders"></a>A quantidade da placa de licença não é válida ao registrar ordens de entrada

## <a name="symptoms"></a>Sintomas

Ao registrar ordens de entrada, você poderá receber a seguinte mensagem de erro:

> A quantidade é inválida.

Se o campo **Política de agrupamento de placas de licença** estiver definido como *Definido pelo usuário* para um item de menu de dispositivo móvel usado para registrar ordens de entrada, você receberá essa mensagem de erro e não poderá concluir o registro.

## <a name="cause"></a>Causa

Quando *Definido pelo usuário* é usado como uma política de agrupamento de placas de licença, o sistema divide o estoque de entrada em chapas de licença separadas, conforme indicado pelo grupo de sequências de unidades. Se os números do lote ou de série forem usados para rastrear o item que está sendo recebido, as quantidades de cada número do lote ou de série deverão ser especificadas por placa de licença registrada. Se a quantidade especificada para uma placa de licença exceder a quantidade que ainda deve ser recebida para as dimensões atuais, você receberá essa mensagem de erro.

## <a name="resolution"></a>Resolução

Ao registrar um item usando um item de menu de dispositivo móvel no qual o campo **Política de agrupamento de chapas de licença** está definido como *Definido pelo usuário*, o sistema poderá exigir que você confirme ou insira números de placas de licença, números do lote ou números de série.

Na página de confirmação da placa de licença, o sistema mostrará a quantidade alocada para a placa de licença atual. Nas páginas de confirmação do número de série ou do lote, o sistema mostrará a quantidade que ainda deve ser recebida na placa de licença atual. Ele também incluirá um campo no qual é possível inserir a quantidade a ser registrada para essa combinação de placa de licença e número do lote ou de série. Nesse caso, verifique se a quantidade que está sendo registrada para a placa de licença não excede a quantidade que ainda deverá ser recebida.

Como alternativa, se muitas placas de licença estiverem sendo geradas no registro de ordem de entrada, o valor do campo **Política de agrupamento da chapa de licença** poderá ser alterado para *Agrupamento de placas de licença*, um novo grupo de sequências de unidades poderá ser atribuído ao item, ou a opção **Agrupamento de placas de licença** para o grupo de sequências de unidades poderá ser desativada.
