---
title: Criar solicitações de manutenção
description: Este artigo explica como criar uma solicitação de manutenção em Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 92f3a2bc3d2a4d5d1c3be0c6dda2674dc3e7d0bb
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016816"
---
# <a name="create-maintenance-requests"></a>Crie solicitações de manutenção

[!include [banner](../../includes/banner.md)]

 

As solicitações de manutenção poderão ser usadas se os funcionários de manutenção ou os funcionários de produção descobrirem que o equipamento exige reparo, mas o reparo não puder ser feito imediatamente.

**Exemplo:** enquanto um funcionário de manutenção está fazendo um reparo, eles descobrem que outro ativo no mesmo local deve ser atendido. Entretanto, a funcionária de manutenção não tem o tempo ou as peças sobressalentes necessárias para realizar o trabalho de reparo. Então, eles criam uma solicitação de manutenção no ativo e inserem uma breve descrição do problema.

A seção **Solicitações de manutenção ativas** do painel **Informações relacionadas** no lado direito da página **Todos os ativos** ou a página **Todos os ativos** (**Gerenciamento de ativos** \> **Assets** \> **Todos os ativos** ou **Ativos ativos**) mostra as solicitações de manutenção ativas anexadas ao ativo selecionado.

1. Selecione **Gerenciamento de ativos** \> **Solicitações de manutenção** \> **Todas as solicitações de manutenção** or **Solicitações de manutenção ativas**.
2. Selecione **Novo**.
3. Na caixa de diálogo **Criar solicitação**, no campo **Tipo de solicitação de manutenção**, selecione o tipo de solicitação de manutenção. Um tipo padrão é sugerido.
4. No campo **Descrição**, insira um nome ou título que descreva resumidamente a solicitação de manutenção.
5. Nos campos **Local funcional** e **Ativo**, selecione um local funcional ou ativo, ou uma combinação de um local funcional e um ativo, conforme necessário. Crie uma solicitação de manutenção sem selecionar um ativo. O ativo poderá ser adicionado à solicitação de manutenção posteriormente. Se o funcionário de manutenção que está conectado estiver relacionado a um recurso relativo a um ativo, o campo **Ativo** será definido automaticamente.

    Se uma solicitação de manutenção já estiver anexada ao ativo selecionado, uma barra de mensagem aparecerá na parte superior da caixa de diálogo **Criar solicitação** para notificá-lo sobre a ID da solicitação de manutenção existente. Uma barra de mensagem notifica-o também se o ativo é coberto por um contrato de garantia.

6. No campo **Nível de serviço**, selecione um nível de serviço que indique a urgência da solicitação.
7. Se você selecionou um ativo na etapa 5, poderá usar os campos **Sintoma de falha**, **Área com falha** e **Tipo de falha** para criar um registro com falha.
8. Se a solicitação de manutenção levou a um tempo de inatividade de manutenção, insira a data e a hora inicial do tempo de inatividade.

    O campo **Iniciado por** é automaticamente definido com seu nome.

10. O campo **Início real** é automaticamente definido com a data e a hora atuais. No entanto, você pode alterar o valor conforme desejado.
11. No campo **Notas**, insira notas adicionais necessárias.
12. Selecione **OK**.

![Criar solicitação de manutenção.](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a>Processamento subsequente de solicitações de manutenção

Após a criação de uma solicitação de manutenção, mas antes de convertê-la em uma ordem de serviço, várias informações devem ser atualizadas nela. Em geral, um planejador ou outro funcionário administrativo conclui essa tarefa.

- Na página **Todas as solicitações de serviço** ou **Solicitações de manutenção de ativos**, selecione a solicitação com a qual deseja trabalhar e **Editar**.

Na exibição de detalhes, é possível atualizar várias informações. Eis alguns exemplos:

- Selecione e verifique o ativo. Se precisar selecionar um ativo diferente depois, você poderá definir a opção **Ativo verificado** como **Não**.
- Selecione um grupo de funcionários de manutenção responsáveis e/ou um funcionário de manutenção responsável. Para obter mais informações sobre a configuração necessária, consulte [Funcionários de manutenção responsáveis](../setup-for-maintenance-requests/responsible-workers.md).
- Selecione um tipo de trabalho de manutenção e, se essas informações forem relevantes, uma grade de trabalho de manutenção relacionada e um comércio de trabalho.
- Nos campos **Latitude** e **Longitude**, insira coordenadas geográficas. Todas as coordenadas adicionadas a uma solicitação de manutenção são transferidas automaticamente a uma ordem de serviço relacionada. 

![Atualizar solicitação de manutenção.](media/04-manage-maintenance-requests.png)

> [!NOTE]
> Se você selecionar um ativo ao criar uma solicitação de manutenção, poderá adicionar uma falha no ativo. Quando a solicitação de manutenção for criada, você poderá adicionar mais falhas, conforme necessário. Para adicionar falhas, selecione **Falha de ativo** na página **Todas as solicitações de manutenção**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]