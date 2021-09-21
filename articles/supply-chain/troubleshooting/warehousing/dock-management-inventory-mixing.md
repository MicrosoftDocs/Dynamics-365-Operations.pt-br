---
title: Tipos de estoque mistos ao usar o perfil de gerenciamento de doca
description: Para um perfil de gerenciamento de doca gerenciar com eficiência a combinação de estoque, uma quebra de cabeçalho de trabalho precisa ser configurada primeiro. Esta página explica como fazer isso.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cc660a2f9839e886240c97a7f60d2e264653074a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475564"
---
# <a name="inventory-types-are-being-mixed-when-using-a-dock-management-profile"></a>Os tipos de estoque estão sendo misturados ao usar um perfil de gerenciamento de doca

## <a name="symptoms"></a>Sintomas

Você está usando *políticas de consolidação de remessa*. Você configurou um *perfil de gerenciamento de doca* para um *perfil de localização*, mas quando o trabalho é criado, os tipos de estoque são combinados na localização final.

## <a name="resolution"></a>Resolução

Os perfis de gerenciamento de doca exigem que o trabalho seja dividido antecipadamente. Em outras palavras, o perfil de gerenciamento de doca espera que um cabeçalho de trabalho não tenha vários locais de armazenamento.

Para o perfil de gerenciamento de doca gerenciar com eficiência a combinação de estoque, uma quebra de cabeçalho de trabalho deve ser configurada.

Neste exemplo, nosso perfil de gerenciamento de doca está configurado de forma que a opção **Tipos de estoque que não devem ser combinados** seja definida como *ID da remessa*, e vamos configurar uma quebra de cabeçalho de trabalho para ele:

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Selecione o **Tipo de ordem de serviço** a ser editado (por exemplo, *Ordens de compra*).
1. Selecione o modelo de trabalho a ser editado.
1. No Painel de Ações, selecione **Editar consulta**.
1. Abra a guia **Classificação** e adicione uma linha com as seguintes configurações:
    - **Tabela** - *Transações de trabalho temporário*
    - **Tabela derivada** - *Transações de trabalho temporário*
    - **Campo** - *ID da remessa*
1. Selecione **OK**.
1. Você retornará à página **Modelos de trabalho**. No Painel de Ação, selecione **Quebras de cabeçalho de trabalho**.
1. No Painel de Ações, selecione **Editar**.
1. Marque a caixa de seleção associada à *ID da remessa* do **Nome do campo**.
1. No Painel de ações, selecione **Salvar**.
