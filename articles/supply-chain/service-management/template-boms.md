---
title: BOMs de modelo
description: Uma BOM (lista de materiais) de modelo fornece uma lista padronizada de componentes de objetos de serviço que são atendidos regularmente.
author: sorenva
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdda8ffaaf4e5696b286273fd5ad770de5349b48
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678140"
---
# <a name="template-boms"></a>BOMs de modelo

[!include [banner](../includes/banner.md)]

Uma BOM (lista de materiais) de modelo fornece uma lista padronizada de componentes para objetos de serviço que são atendidos regularmente. Os componentes listados na BOM de modelo representam os subcomponentes individuais do objeto de serviço. Ao aplicar uma BOM de modelo a um objeto de serviço, você pode manter um registro dos subcomponentes que foram substituídos no objeto de serviço.

Para aplicar uma BOM de modelo a um contrato de serviço ou uma ordem de serviço, anexe-a a uma relação de objeto de serviço.

> [!NOTE]
> Você pode aplicar somente uma BOM de modelo a um objeto de serviço.

## <a name="create-a-template-bom"></a>Criar uma BOM de modelo

A tabela a seguir contém informações sobre os vários métodos que podem ser usados para criar uma BOM de modelo.

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Método</p></th>
<th><p>Descrição</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Produção</p></td>
<td><p>A BOM de modelo se baseia em uma ordem de produção. Essa opção se aplicará somente se você operar em um ambiente de produção. O benefício é que você tem uma lista detalhada e atualizada dos componentes de um item.</p></td>
</tr>
<tr class="even">
<td><p>BOM de item</p></td>
<td><p>A BOM de modelo se baseia na BOM de um item. A BOM do item, diferentemente da BOM de produção, é uma lista estática dos componentes que compõem um item.</p></td>
</tr>
<tr class="odd">
<td><p>Modelo existente</p></td>
<td><p>O modelo se baseia na BOM de um modelo existente.</p></td>
</tr>
<tr class="even">
<td><p>Manual</p></td>
<td><p>Se você souber quais peças sobressalentes geralmente são substituídas em um objeto de serviço, será possível criar a BOM de modelo manualmente. Esse modelo ajuda a verificar se os componentes incluídos no modelo refletem os requisitos reais do local de trabalho.</p></td>
</tr>
</tbody>
</table>

## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a>Aplicar a BOM de modelo a um contrato de serviço ou uma ordem de serviço

Você pode aplicar uma BOM de modelo a um contrato de serviço, a uma ordem de serviço, ou a ambos. O contrato de serviço normalmente cobre um relacionamento de longo prazo com um cliente. O histórico de substituições registrado na BOM de serviço contém dados úteis para o contrato de serviço.

Também é possível aplicar uma BOM de modelo a uma ordem de serviço para registrar o histórico do serviço que foi executado em um objeto de serviço.

## <a name="copy-the-history-of-a-service-bom"></a>Copiar o histórico de uma BOM de serviço

Você pode copiar o histórico de uma linha de BOM de serviço de um contrato de serviço em outro. Ao copiar o histórico de serviço entre contratos, você pode preservar o registro de substituições de um item.

### <a name="example"></a>Exemplo

Você configurou um contrato de serviço de três anos para o carro de um cliente. Durante esse período, o cliente se acostuma com o bom nível de serviço prestado pela empresa. Assim, após a expiração do contrato, o cliente quer firmar um novo. Agora você pode negociar um contrato mais favorável para a empresa. Como o registro dos componentes substituídos pode ser útil no futuro, você copia o histórico da BOM de serviço no novo contrato.

## <a name="modify-the-template-bom"></a>Modificar a BOM de modelo

Se um BOM de modelo não tiver sido anexada a um objeto de serviço, você poderá modificar ou excluir suas linhas. Depois de anexar a BOM de modelo a um objeto de serviço, você só poderá modificar a versão local da BOM. Se quiser duplicar a configuração de uma versão local de uma BOM de modelo, poderá criar uma nova BOM de modelo com base na versão local. Para obter mais informações, consulte [Modificar uma BOM de Serviço](modify-service-bom.md).

Ao substituir um item na BOM, você poderá registrar a substituição na linha de BOM no Designer de BOM. Se desejar, você poderá criar uma linha de ordem de serviço para o objeto de substituição. Ao criar uma linha de ordem de serviço, você poderá faturar o item de substituição. Caso você não crie uma linha de ordem de serviço para uma substituição, o registro da substituição será mantido a fim de rastrear o histórico do objeto de serviço.

## <a name="change-how-information-on-the-bom-line-is-displayed"></a>Alterar como as informações na linha da BOM são exibidas

É possível alterar o modo como as informações na linha de BOM são exibidas para todas as BOM de modelo e de serviço. As alterações são aplicadas a todas as BOMs de modelo e de serviço. Isso inclui aquelas que são anexadas aos objetos de serviço.

## <a name="set-up-number-sequences-for-template-boms"></a>Configurar sequências numéricas para as BOMs de modelo

Para usar BOMs de modelo, você deve configurar duas sequências numéricas. Configure uma sequência numérica para a BOM de modelo e uma para o número da linha do histórico da BOM.

> [!NOTE]
> As sequências numéricas são usadas para alocar identificadores para registros que os exigem. Para poder atribuir uma sequência numérica a uma BOM de modelo ou a um número da linha do histórico da BOM, você deve configurar códigos de sequências numéricas.

## <a name="set-up-number-sequences"></a>Configurar sequências numéricas

1. Na página de listagem **Sequências numéricas**, crie sequências numéricas para BOMs de modelo e para o número da linha do histórico da BOM.
1. Selecione **Gerenciamento de serviços** \> **Configuração** \> **Parâmetros de gerenciamento de serviços**.
1. Selecione **Sequências numéricas** e, depois, um código de sequência numérica para as referências de sequência numérica criadas no formulário **Sequências numéricas**.
1. Feche o formulário para salvar suas alterações.

> [!NOTE]
> O número da linha do histórico da BOM é usado pelo sistema para associar as transações no histórico da BOM a um contrato de serviço ou a uma ordem de serviço. O número não é exibido na interface do usuário.

## <a name="see-also"></a>Consulte também

[Criar uma BOM de modelo](create-template-bom.md)

[Gerenciar BOMs de modelo nas relações de objeto](manage-template-boms-on-object-relations.md)

[Modificar uma BOM de Serviço](modify-service-bom.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
