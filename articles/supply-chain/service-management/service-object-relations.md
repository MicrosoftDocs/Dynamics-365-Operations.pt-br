---
title: Relações do objeto de serviço
description: Você pode criar relações de objeto de serviço entre um objeto de serviço e um contrato de serviço ou uma ordem de serviço.
author: kamaybac
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7eb5b185ca2ef5903eb1739edfdd7b60749babd4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576343"
---
# <a name="service-object-relations"></a>Relações do objeto de serviço 

[!include [banner](../includes/banner.md)]

Você pode criar relações de objeto de serviço entre um objeto de serviço e um contrato de serviço ou uma ordem de serviço. Ao criar uma relação, você anexa o objeto de serviço ao contrato de serviço ou à ordem de serviço.

Quando a relação tiver sido criada, você anexa o objeto de serviço a qualquer linha no contrato de serviço ou na ordem de serviço.

## <a name="template-boms"></a>BOMs de modelo

Você também pode especificar uma BOM de modelo para a relação de objeto. A BOM de modelo é uma lista de materiais para o objeto no qual você realiza um serviço. Se você substituir uma parte componente do objeto de serviço durante uma visita de serviço, você pode registrar essa alteração na BOM de serviço usando o formulário Objetos de serviço.

## <a name="example"></a>Exemplo

Você cria um contrato de serviço para atender dois elevadores no local do cliente.
O contrato de serviço tem a identificação ID SAL-001.

Os elevadores foram configurados no formulário Objetos de serviço como objetos, EL-S/1000 e EL-L/1000.

Você anexa os objetos de serviço (EL-S/1000 e EL-L/1000) ao contrato de serviço.

Você deseja registrar as alterações na BOM para o objeto de serviço enquanto substitui partes componentes do objeto; assim, anexa uma BOM de serviço à relação de objeto de serviço, conforme descrito na tabela a seguir.

| Objeto de serviço | Relação - Contrato de serviço | BOM de serviço   |
|----------------|------------------------------|---------------|
| EL-S/1000      | ID SAL-001                   | BOM-EL-S/1000 |
| EL-L/1000      | ID SAL-001                   | BOM-EL-L/1000 |

Como há relações de objeto de serviço para o contrato, agora você pode criar linhas de contrato de serviço com esses objetos, conforme descrito na tabela a seguir.

| Tipo de transação | Categoria           | Objeto de serviço |
|------------------|--------------------|----------------|
| Hora             | Inspeção         | EL-S/1000      |
| Hora             | Limpeza da caixa de engrenagens  | EL-S/1000      |
| Item             | Material de limpeza | EL-S/1000      |
| Hora             | Inspeção         | EL-L/1000      |
| Hora             | Limpeza da caixa de engrenagens   | EL-L/1000      |
| Item             | Material de limpeza | EL-L/1000      |

Em uma visita de serviço, é necessário substituir a caixa de embreagens do elevador EL-S/1000. Para substituir uma parte componente do objeto, você pode acessar o Designer de BOM usando a relação de objeto de serviço configurada para o contrato de serviço atual.

Acessar o Designer de BOM usando uma relação de objeto de serviço

1. Contratos de serviço
2. Clique duas vezes em um contrato de serviço ou clique em Contrato de serviço para criar um novo contrato de serviço.
3. Clique na guia Configuração.
4. Clique em Objetos de serviço para anexar uma BOM de modelo ao contrato de serviço.
5. No formulário Objetos de serviço, clique em Designer para abrir o formulário Designer para modificar a BOM de modelo.

## <a name="automatically-created-service-orders"></a>Ordens de serviço criadas automaticamente

Se você criar ordens de serviço automaticamente para um contrato de serviço, as relações de objeto de serviço no contrato também estarão nas ordens de serviço criadas.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]