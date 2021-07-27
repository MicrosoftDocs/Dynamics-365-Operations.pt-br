---
title: Integração da nota
description: Este tópico descreve a integração de dados da nota em gravação dupla.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 3ff40011ac60c47f6ed667adfcf01bc727334f13
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358970"
---
# <a name="note-integration"></a>Integração da nota

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Durante processos comerciais, os usuários do Microsoft Dynamics 365 geralmente coletam informações sobre seus clientes. Essas informações são registradas como atividades e notas. Este tópico descreve a integração de dados da nota em gravação dupla.

As informações do cliente podem ser classificadas das seguintes maneiras:

+ **Informações acionáveis que um usuário do Dynamics 365 gerencia em nome de um cliente** – Por exemplo, a Contoso (um usuário do Dynamics 365) está realizando um programa de TV. Um dos clientes da Contoso (um cliente) quer participar do programa. O cliente pede ao funcionário da Contoso para reservar uma vaga no programa de TV para ele. A reserva ocorre no calendário de participantes do evento da Contoso.
+ **Informações Acionáveis para um usuário do Dynamics 365** – por exemplo, um cliente que esteja comprando uma unidade de superfície insere instruções especiais que indicam que o dispositivo deve estar embalado antes da entrega. Essas instruções são informações acionáveis que devem ser gerenciadas pelo funcionário da Contoso responsável pela embalagem.
+ **Informações não acionáveis** – Por exemplo, um cliente visita uma loja da Contoso e, durante uma conversa com um funcionário da loja, ele mostra interesse em jogos e acessórios do *Halo*. O associado da loja anota essas informações. O mecanismo de recomendações do produto o utiliza para fazer recomendações ao cliente.

Em geral, as informações acionáveis são capturadas como *atividades* nos aplicativos Finance and Operations e de engajamento do cliente. As informações não acionáveis são capturadas como *notas* nos aplicativos Finance and Operations e como *anotações* nos aplicativos de engajamento do cliente.

> [!TIP]
> Embora as notas sejam destinadas a informações não acionáveis, os aplicativos não impedem que você as utilize para armazenar e manipular informações acionáveis, caso queira usá-las dessa forma.

No momento, a Microsoft está lançando funcionalidades para a integração de notas. (A funcionalidade para a integração de atividades será liberada posteriormente). A integração da nota está disponível para clientes, fornecedores, ordens de venda e ordens de compra.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Criar uma nota em um aplicativo de engajamento do cliente

Para criar uma nota em um aplicativo de engajamento do cliente e sincronizá-la com um aplicativo Finance and Operations, siga estas etapas.

1. No aplicativo engajamento do cliente, abra o registro da conta de um cliente.
2. No painel **Linha de tempo**, selecione o sinal de adição (**+**) e, em seguida, selecione **Nota** para criar uma nota.

    ![Criando uma nota em um aplicativo de engajamento do cliente.](media/notes-ce-1.png)

3. Informe um título e uma descrição e selecione **Adicionar nota**.

    ![Inserindo um título e uma descrição.](media/notes-ce-2.png)

    A nova nota é adicionada à linha do tempo do cliente.

    ![Nova nota na linha do tempo do cliente.](media/notes-ce-3.png)

4. Entre no aplicativo Finance and Operations e abra o mesmo registro de cliente. Lembre-se de que o botão **Anexos** (símbolo de clipe de papel) no canto superior direito indica que o registro tem um anexo.

    ![Notificação sobre um anexo.](media/notes-ce-4.png)

5. Selecione o botão **Anexos** para abrir a página **Anexos**. Você deve encontrar a nota criada no aplicativo de engajamento do cliente.

    ![Observação do aplicativo de engajamento do cliente.](media/notes-ce-5.png)

Todas as atualizações da nota são sincronizadas para frente e para trás entre o aplicativo Finance and Operations e o aplicativo de engajamento do cliente.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Criar uma nota em um aplicativo do Finance and Operations

Também é possível criar uma nota em um aplicativo Finance and Operations e ela será sincronizada em um aplicativo de engajamento do cliente.

Para criar uma nota em um aplicativo Finance and Operations e sincronizá-la para um aplicativo de engajamento do cliente, siga estas etapas.

1. No aplicativo Finance and Operations na página **Anexos**, selecione **Nova** \> **Nota**.

    ![Criando uma nota no aplicativo Finance and Operations.](media/notes-fo-1.png)

2. Insira um título e um breve conjunto de instruções e selecione **Salvar**.

    ![Inserindo um título e instruções.](media/notes-fo-2.png)

3. No aplicativo de engajamento do cliente, atualize o registro. Você deve encontrar a nova nota na linha do tempo.

    ![Nova nota na linha do tempo no aplicativo de engajamento do cliente.](media/notes-fo-3.png)

Você pode classificar uma nota como interna ou externa.

- No aplicativo Finance and Operations, na página **Anexos**, abra a anotação e, no campo **Restrição**, selecione **Interno** ou **Externo**.

    ![Campo de restrição.](media/notes-fo-4.png)

Você também pode cria uma URL.

1. No aplicativo Finance and Operations, na página **Anexos**, selecione **Nova** \> **URL**.
2. Insira um título e uma URL.
3. No campo **Restrição**, selecione **Interno** ou **Externo**.

    ![Criando uma URL no aplicativo Finance and Operations.](media/notes-fo-5.png)

4. Selecione **Salvar**.

    Como os aplicativos do engajamento do cliente não têm um tipo de URL, a URL é integrada com a gravação dupla como uma nota.

    ![URL aparecendo uma nota em um aplicativo de engajamento do cliente.](media/notes-ce-6.png)

> [!NOTE]
> Não há suporte para anexos de arquivo.

## <a name="templates"></a>Modelos

A integração da nota inclui um conjunto de mapas de tabelas que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

| Aplicativo Finance and Operations | Aplicativo Customer Engagement | descrição |
|----------------------------|-------------------------|-------------|
| [Anexos do Cliente](mapping-reference.md#230) | Anotações | Empresas que usam texto sem formatação e URLs para capturar informações específicas do cliente (para organizações e pessoas). |
| [Anexos de documentos do fornecedor](mapping-reference.md#231) | Anotações | Empresas que usam texto sem formatação e URLs para capturar informações específicas do fornecedor (para organizações e pessoas). |
| [Anexos de documento de cabeçalho de ordem de venda](mapping-reference.md#229) | Anotações | Empresas que usam texto sem formatação e URLs para capturar informações específicas da ordem de venda. |
| [Anexos de documento de cabeçalho de ordem de compra](mapping-reference.md#232) | Anotações | Empresas que usam texto sem formatação e URLs para capturar informações específicas da ordem de compra. |

## <a name="limitations"></a>Limitações

Depois de instalar a solução de notas, não será possível desinstalá-la. 

Para obter mais informações, consulte [Referência de mapeamento de gravação dupla](mapping-reference.md).
