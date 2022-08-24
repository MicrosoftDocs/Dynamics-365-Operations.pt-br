---
title: Manter certificação do fornecedor
description: Este artigo descreve as etapas que os fornecedores podem usar para manter certificações usando o espaço de trabalho de colaboração do fornecedor.
author: v-kiarnd
ms.date: 04/27/2021
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: v-kiarnd
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e6742037d04cb21c153af3cd22d1dcb91e3d64e8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268492"
---
# <a name="maintain-vendor-certification"></a>Manter certificação do fornecedor

[!include [banner](../includes/banner.md)]

Este artigo descreve as etapas que os fornecedores podem usar para manter certificações usando o **Espaço de trabalho de colaboração do fornecedor**. Exemplos de certificações podem incluir uma empresa WBE (Woman Business Enterprise) ou LEED (Leadership in Energy and Environment Design). Os fornecedores precisarão inserir informações de certificação no espaço de trabalho **Informações do fornecedor**. A partir daí, os fornecedores selecionarão **Mais detalhes** e, depois, **Certificações**.

## <a name="turn-on-the-vendor-certification-feature"></a>Ativar o recurso de certificação do fornecedor

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar a página [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo** - *Contas a pagar*
- **Nome do recurso** - *Habilitar o gerenciamento de certificação de colaboração do fornecedor*

## <a name="add-a-new-certification"></a>Adicionar uma nova certificação

Para adicionar uma nova certificação, selecione o botão **Adicionar** localizado acima da grade **Certificação** no espaço de trabalho **Informações do fornecedor**. Digite as seguintes informações:

- Número de certificação
- Tipo de certificação
- Organização de certificação
- Data de certificação
- Valor de passivo, se aplicável
- Data de efetivação
- Data de expiração
- Comentários, opcional

Se houver documentos relacionados à certificação específica, você poderá anexá-los selecionando o botão **Documento**.

As certificações inseridas pelos fornecedores nesta página receberão uma origem de "Fornecedor". Você pode inserir informações de certificado em nome do fornecedor em contas bancárias de fornecedor. As informações serão exibidas aqui e a fonte será exibida como **Cliente**.

Os fornecedores podem editar ou excluir certificações conforme necessário.

## <a name="vendor-collaboration-generated-certification-records"></a>Registros de certificação gerados pela colaboração de fornecedor

Após as informações de certificação serem adicionadas por um fornecedor, as informações ficarão visíveis na página **Registros de certificação gerados pela colaboração de fornecedor**. Para abrir a página, Acesse **Contas a pagar > Consultas > Relatórios do fornecedor > Registros de certificação gerados pela colaboração de fornecedor**. Por padrão, todos os registros de certificação modificados são visíveis. Um atendente de Contas a pagar pode visualizar as alterações e validar as informações por meio de seu processo de confirmação para validar. Quando as informações forem confirmadas, o registro de certificação listado na página pode ser selecionado e marcado como avaliado. Marcar o registro como avaliado o removerá da lista padrão.

Todas as alterações de certificação ficarão visíveis na página **Registros de certificação gerados pela colaboração de fornecedor**. Se uma alteração não for exibida na página, você pode visualizá-la ajustando os filtros para a conta do fornecedor, intervalo de data efetivo, ou selecionando se quer incluir informações para alterações de certificação que foram avaliadas.

