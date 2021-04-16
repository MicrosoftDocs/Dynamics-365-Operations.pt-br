---
title: Criar uma BOM de modelo
description: Você pode criar uma BOM de modelo usando uma variedade de métodos.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 781df7611ec1e3ee9d3013f971232700df38ada0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836293"
---
# <a name="create-a-template-bom"></a>Criar uma BOM de modelo   

[!include [banner](../includes/banner.md)]


Você pode criar uma BOM de modelo usando qualquer um dos seguintes métodos. Para todos os métodos, os campos **Data de início** e **Data de término** são opcionais e apenas informativos.

## <a name="create-a-template-bom-manually"></a>Criar uma BOM de modelo manualmente

1.  Acesse **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.

2.  Selecione **Novo** para abrir o formulário **Criar BOM de modelo**.

3.  Em **Copiar linhas de BOM de referência**, selecione a opção **Manual**.

4.  No campo **Número de item**, insira um item do tipo **BOM**.

5.  No campo **Nome**, digite um nome para o modelo.

6.  Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.

7.  Selecione **OK**.

Uma nova BOM de modelo em branco é criada.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Criar uma BOM de modelo baseada em outra BOM de modelo

1.  Selecione **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.

2.  Selecione **Novo** para abrir o formulário **Criar BOM de modelo**.

3.  Em **Copiar linhas de BOM de referência**, selecione a opção **BOM de modelo**.

4.  No campo **Número de referência**, selecione uma BOM de modelo existente para copiar para sua nova BOM de modelo.

5.  No campo **Nome**, digite um nome para o modelo.

6.  Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.

7.  Selecione **OK**.

Uma nova BOM de modelo é criada usando linhas que correspondem às linhas da BOM de modelo original.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Criar uma BOM de modelo baseada em um BOM de itens

1.  Selecione **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.

2.  Selecione **Novo** para abrir o formulário **Criar BOM de modelo**.

3.  Em **Copiar linhas da BOM da referência**, selecione **BOM**.

4.  No campo **Número de referência**, selecione uma versão da BOM. Um item do tipo BOM é copiado para **Número de item**.

5.  No campo **Nome**, digite um nome para o modelo.

6.  Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.

7.  Selecione **OK**.

Uma nova BOM de modelo é criada usando linhas que correspondem às linhas da BOM listada em **Lista de materiais**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Criar uma BOM de modelo baseada em um BOM de produção

1.  Selecione **Gerenciamento de serviços** \> **Configuração** \> **Objetos de serviço** \> **BOMs de modelo**.

2.  Selecione **Novo** para abrir o formulário **Criar BOM de modelo**.

3.  Em **Copiar linhas da BOM da referência**, selecione **Produção**.

4.  No campo **Número de referência**, selecione uma BOM de produção.

5.  No campo **Nome**, digite um nome para o modelo.

6.  Nos campos **Data de início** e **Data de término**, insira um intervalo de datas no qual a BOM de modelo está ativa.

7.  Selecione **OK**.

Uma nova BOM de modelo é criada usando linhas que correspondem às linhas da BOM listada em **BOM**.

## <a name="see-also"></a>Consulte também

[BOMs de modelo](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]