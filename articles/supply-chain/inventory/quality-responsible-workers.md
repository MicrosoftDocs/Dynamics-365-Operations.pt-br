---
title: Trabalhadores responsáveis por aprovar não conformidades
description: Este tópico descreve como configurar trabalhadores que são responsáveis por aprovar não conformidades.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b764baf0983dbca75d52ea9cdd063cebda80a08d39cf3a5c929f15858e2597c1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768158"
---
# <a name="workers-responsible-for-approving-nonconformances"></a>Trabalhadores responsáveis por aprovar não conformidades

[!include [banner](../includes/banner.md)]

Este tópico descreve como configurar trabalhadores que são responsáveis por aprovar não conformidades.

As não conformidades devem ser aprovadas para que os usuários possam começar a inserir detalhes, como correções ou operações. Para que os usuários possam aprovar ou rejeitar não conformidades, sua ID de usuário (registro de usuário) deve estar vinculada a um registro de trabalhador. Opcionalmente, você pode configurar trabalhadores que sejam responsáveis pela qualidade e, em seguida, permitir que um trabalhador aprove o trabalho em nome de outro trabalhador.

## <a name="enable-a-user-for-nonconformance-processing"></a>Habilitar um usuário para o processamento de não conformidade

Para que um usuário possa aprovar ou rejeitar não conformidades, você deve vincular seu registro de usuário a um registro de trabalhador. Os campos de aprovação podem então ser automaticamente definidos, e o usuário atual pode ser preenchido de forma automática na folha de ponto. Para que o usuário possa usar as notas do documento, é necessário ativar o manuseio de documentos nas opções do usuário.

1. Acesse **Administração do sistema \> Usuários \> Usuários**.
1. Localize e abra o usuário que deve ser capaz de aprovar ou rejeitar não conformidades.
1. Defina o campo **Pessoa** como o nome do trabalhador relacionado ao registro de usuário atual.
1. No Painel de Ações, selecione **Opções do usuário**.
1. Na página **Opções** do registro de usuário atual, na guia **Preferências**, defina a opção **Habilitar manuseio de documentos** como *Sim*.
1. Feche as páginas.

## <a name="define-workers-that-are-responsible-for-quality"></a>Definir trabalhadores responsáveis pela qualidade

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Trabalhadores responsáveis pela qualidade**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **Trabalhador**, selecione o trabalhador que insere os dados de qualidade.
4. No campo **Trabalhador responsável**, selecione o trabalhador para o qual o trabalhador selecionado insere trabalhos. Quando as não conformidades forem criadas e atualizadas, esse trabalhador será inserido por padrão nos campos **Trabalhador**.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do gerenciamento de qualidade](quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Encargos de qualidade](quality-charges.md)
- [Zonas de quarentena para não conformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico para não conformidades](quality-diagnostic-types.md)
- [Encargos de qualidade para não conformidades](quality-charges.md)
- [Operações para não conformidades](quality-operations.md)
- [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
