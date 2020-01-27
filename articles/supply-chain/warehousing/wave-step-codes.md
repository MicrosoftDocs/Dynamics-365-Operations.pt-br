---
title: Códigos da etapa da onda
description: Este tópico fornece uma visão geral dos códigos da etapa da onda e como são usados.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1a1a32495b63a5a67a49bf3b02710aba63c1e2f0
ms.sourcegitcommit: bfd6142569196a060e3f37893c78f00c40a2a18c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946181"
---
# <a name="wave-step-codes"></a>Códigos da etapa da onda

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

Os códigos da etapa da onda são códigos que os usuários podem configurar e usar para vincular instâncias específicas de métodos da onda a um modelo correspondente. Os modelos incluem modelos para reabastecimento, transporte em contêineres, impressão de etiquetas, criação de carga e classificação.

Quando os códigos da etapa da onda não forem usados, os usuários deverão inserir texto livre para fazer referência a um modelo específico da instância de método da onda. O texto livre é propenso a erros, pois os usuários devem verificar se o texto da etapa da onda adicionado para um método específico da etapa da onda em um modelo da onda corresponde exatamente ao texto da etapa da onda em modelo de destino.

Os códigos da etapa da onda para um tipo específico da etapa da onda são configurados em uma página separada. Para cada instância de método da etapa da onda em um modelo da onda que requer um código da etapa da onda, o código da etapa da onda deve ser selecionado na lista suspensa. A seleção na lista suspensa substitui a entrada de texto livre e ajuda a reduzir o risco e o impacto de erros humanos. Códigos de configuração são usados para vincular um método da etapa da onda a um modelo de destino da onda para o método.

> [!NOTE]
> O uso do recurso códigos de etapa da onda é opcional. Ela é habilitada em toda a organização para todas as entidades legais.

## <a name="setup-demo"></a>Demonstração de instalação 

Para esta demonstração, os dados de demonstração devem ser instalados, e você deve usar a empresa de dados de demonstração **USMF** .

### <a name="enable-wave-step-codes"></a>Habilitar códigos da etapa da onda

Siga estas etapas para ativar o recurso de códigos da etapa da onda.

1. Vá para **Gerenciamento de Recursos**.
2. Selecione para habilitar o recurso chamado **Código de Etapa de Onda para Toda a Organização**.

Todos os textos livres da etapa da onda existentes em todas as entidades legais são atualizados para a nova estrutura. Depois que essa atualização for concluída para todas as entidades legais, o recurso será habilitado. Se o recurso não puder ser habilitado para uma ou mais entidades legais, o recurso não estará habilitado para nenhuma entidade legal.

Durante a habilitação, serão feitas validações durante a atualização de dados. Se a atualização falhar, você receberá uma mensagem de erro. Uma atualização pode falhar devido aos seguintes conflitos:

- Existem textos livres da etapa da onda.
- Existem Personalizações.
- Um texto livre da etapa da onda que é associado a uma instância de método da etapa da onda não corresponde ao tipo de modelo esperado.

Depois de resolver os conflitos identificados durante validações, você pode tentar habilitar o recurso.

Quando o recurso for habilitado, a página **Códigos da etapa da onda** (**Gerenciamento de depósito \> Configuração \> Ondas \> Códigos da etapa da onda**) ficará disponível. Esta página lista os códigos da etapa da onda que foram atualizados quando o recurso Código de Etapa de Onda para Toda a Organização for habilitado.

### <a name="create-new-wave-step-codes"></a>Criar novos códigos da etapa da onda

Você pode usar a página **Códigos da etapa da onda** para criar e excluir códigos da etapa da onda.

Cada novo código da etapa e sua ID associada devem ser exclusivos em todos os tipos de etapa da onda e devem ser definidos para um tipo específico de etapa da onda.

### <a name="apply-wave-step-codes"></a>Aplicar códigos da etapa da onda

Depois de definir os códigos da etapa da onda apropriados, eles podem ser aplicados aos métodos da etapa da onda.

Para aplicar códigos da etapa da onda, vá para o modelo apropriado de destino. Veja a seguir os modelos de destino para os quais os códigos da etapa da onda estão designados para apontar:

- **Modelos de reabastecimento:** Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento
- **Modelos de criação de carga:** Gerenciamento de depósito \> Configuração \> Carga \> Modelos de criação de carga
- **Modelos de classificação:** Gerenciamento de depósito \> Configuração \> Embalagem \> Modelos de classificação de saída
- **Modelos de transporte em contêineres:** Gerenciamento de depósito \> Configuração \> Contêineres \> Modelos de criação de contêiner
- **Modelos de impressão de etiquetas:** Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Modelos de etiquetas da onda

Os modelos nesta lista são aplicados quando referidos em um método da etapa da onda que está selecionado em um modelo da onda. Quando o código da etapa da onda de um processo de método da onda em um modelo da onda corresponder ao código da etapa da onda em um dos tipos de modelos, o modelo será aplicado.

### <a name="sample-scenario"></a>Cenário de exemplo

O procedimento a seguir ajuda a garantir que o método de reabastecimento criado seja aplicado para o modelo da onda.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Códigos da etapa da onda** e crie um código da etapa da onda para o tipo **Reabastecimento**.
2. Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento** e crie o modelos de reabastecimento.
3. No modelo de reabastecimento, selecione o código da etapa da onda criada para o tipo **Reabastecimento**.
4. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos da onda** e selecione o modelo da onda que você deseja usar.
5. No modelo, na guia rápida **Métodos**, selecione o método **Reabastecimento**.
6. No campo **Código da etapa da onda**, selecione o código da etapa da onda selecionada no modelo de reabastecimento.

Essas etapas são executadas para cada entidade legal.
