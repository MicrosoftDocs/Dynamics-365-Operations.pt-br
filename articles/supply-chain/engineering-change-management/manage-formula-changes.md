---
title: Gerenciar alterações nas fórmulas e seus ingredientes
description: Este tópico descreve como realizar o gerenciamento de fórmula e gerenciar alterações nos dados mestres de fabricação de processos.
author: t-benebo
ms.date: 05/19/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: c65f929120d2501fa3873880179a9b53ab79c60c73fd4d597fb6151b1c5bb2b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720387"
---
# <a name="manage-changes-in-formulas-and-their-ingredients"></a>Gerenciar alterações nas fórmulas e seus ingredientes

[!include [banner](../includes/banner.md)]

Se você estiver usando os recursos de fabricação de processos do Microsoft Dynamics 365 Supply Chain Management, também poderá usar os recursos de gerenciamento de fórmula relacionados para gerenciar as seguintes alterações:

- **Fórmula e itens de planejamento:** gerencie alterações de ingredientes em fórmulas e seus coprodutos e subprodutos.
- **Coprodutos e subprodutos:** edite as quantidades e outras informações dos coprodutos e subprodutos em uma fórmula.
- **Itens de peso variável:** gerencie alterações para itens de peso variável.

## <a name="turn-on-this-feature-in-your-system"></a>Ative este recurso no seu sistema

Para usar esse recurso, você deve concluir as seguintes tarefas:

1. Habilite o recurso *Gerenciamento de alterações de engenharia* e sua chave de configuração conforme descrito em [Visão geral do gerenciamento de alterações de engenharia](product-engineering-overview.md). Conforme mencionado neste tópico, certifique-se de ativar também a chave de licença **Gerenciamento de alterações para fabricação de processos**, que está aninhada abaixo da chave de licença principal **Gerenciamento de Alterações de Engenharia**.
1. Ative o recurso *Gerenciar alterações nas fórmulas e seus ingredientes* em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="feature-naming-conventions"></a>Convenções de nomenclatura de recursos

Na documentação e interface do usuário (IU) do Supply Chain Management, a funcionalidade de gerenciamento de alterações costuma ser referida como *gerenciamento de alteração de engenharia*, e os produtos gerenciáveis são geralmente referidos como *produtos de engenharia*. Embora essa terminologia não seja geralmente associada ao gerenciamento de fórmula para a fabricação de processos, você deve considerar o gerenciamento de alterações de engenharia simplesmente como gerenciamento de alterações e nos produtos de engenharia como produtos com versão.

## <a name="work-with-formula-change-management-features"></a>Trabalhar com recursos de gerenciamento de alterações de fórmula

A lista a seguir resume como os recursos de gerenciamento de alterações de engenharia se aplicam ao gerenciamento de fórmula. Também fornece links para mais informações. Como o gerenciamento de alterações de fórmula aproveita os recursos de gerenciamento de alterações de engenharia, você deve entender como funciona o gerenciamento de alterações de engenharia em geral, para que possa usá-lo para gerenciar suas fórmulas e seus ingredientes.

- **Gerenciamento centralizado de dados do produto**: configure uma organização que, por meio de um processo de liberação gerenciado, garanta que dados precisos e relevantes do produto estejam disponíveis para usuários em toda a empresa. Para obter mais informações, consulte [Empresas de engenharia e regras de propriedade de dados](engineering-org-data-ownership-rules.md).
- **Controle de versão de produto**: rastreie alterações em produtos por meio de versões de produtos e controle o produto em todos os estágios da cadeia de fornecimento. Dessa forma, você pode acompanhar as mudanças em suas formulações. Para obter mais informações, consulte [Versões de engenharia e categorias de produto de engenharia](engineering-versions-product-category.md).
- **Gerenciamento do ciclo de vida do produto**: gerencie a visibilidade dos dados do produto em toda a organização e controle a disponibilidade das versões do produto em cada estágio da cadeia de fornecimento. Você tem controle detalhado sobre quando uma versão do produto pode ser usada em processos de negócios específicos e pode criar seus próprios estados de ciclo de vida para atender às suas necessidades de negócios. Para obter mais informações, consulte [Estados e transações de ciclo de vida do produto](product-lifecycle-state-transactions.md).
- **Gerenciamento de alterações de fórmula**: os usuários de toda a organização podem solicitar alterações nas fórmulas. Use ordens de alteração para avaliar e documentar o impacto das mudanças propostas. Adicione fluxos de trabalho para gerenciar o processo de alterações e a liberação de novas versões do produto e sua fórmula. Para obter mais informações, consulte [Gerenciar alterações de produtos de engenharia](engineering-change-management.md).
- **Controle de preparação**: use verificações do sistema e orientação do usuário (questionários e listas de verificação) para garantir que todos os dados necessários do produto sejam totalmente inseridos antes do lançamento do produto. Para obter mais informações, consulte [Preparo do produto](product-readiness.md).
- **Funcionalidade de liberação de produto aprimorada**: libere versões totalmente definidas de um produto e sua fórmula de uma organização (entidade legal) para outras entidades legais. Você pode até decidir se as informações do produto devem ser revisadas ou editadas antes do lançamento. Para obter mais informações, consulte [Liberar estruturas de produtos](release-product-structure.md).

Observe que a maioria dos tópicos vinculados na lista anterior fornecem exemplos baseados em listas de materiais (BOMs). No entanto, as fórmulas funcionam de maneira semelhante. Aqui estão alguns conceitos adicionais que são úteis saber quando você usa o gerenciamento de alterações (ou apenas o gerenciamento de alterações de fórmula) para gerenciar fórmulas e BOMs:

- Para cada [categoria de engenharia de produto](engineering-versions-product-category.md), você pode especificar o tipo de produção (BOM, fórmula ou item de planejamento). Você também pode especificar se o suporte de peso variável é necessário para produtos que usam essa categoria.
- Coprodutos e subprodutos não são produtos de engenharia. Portanto, eles não têm versões. Se você precisar alterá-los, basta criar um produto. Essa abordagem torna a manutenção mais fácil.
- Você pode gerenciar itens finais que são BOMs e que possuem itens de fórmula secundários. A funcionalidade funcionará para qualquer combinação de BOMs que contenham fórmulas e/ou fórmulas que contenham BOMs.
