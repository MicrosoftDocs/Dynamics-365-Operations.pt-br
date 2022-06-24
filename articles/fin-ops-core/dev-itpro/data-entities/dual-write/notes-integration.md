---
title: Integração da nota
description: Este artigo descreve a integração de dados da nota em gravação dupla.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 8e1444aa311bb2dc74705a3791e58c3187ecd8ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876705"
---
# <a name="note-integration"></a>Integração da nota

[!include [banner](../../includes/banner.md)]



Durante processos comerciais, os usuários do Microsoft Dynamics 365 geralmente coletam informações sobre seus clientes. Essas informações são registradas como atividades e notas. Este artigo descreve a integração de dados da nota em gravação dupla.

As informações do cliente podem ser classificadas das seguintes maneiras:

+ **Informações acionáveis que um usuário do Dynamics 365 manipula em nome de um cliente**, por exemplo, Contoso (um usuário do Dynamics 365) está realizando uma apresentação de jogo. Um dos clientes da Contoso (um cliente) quer participar da apresentação de jogos. O cliente solicita que um funcionário da Contoso marque um slot nas apresentações de jogos. A reserva ocorre no calendário do participante do evento do Contoso.
+ **Informações Acionáveis para um usuário do Dynamics 365** – por exemplo, um cliente que esteja comprando uma unidade de superfície insere instruções especiais que indicam que o dispositivo deve estar embalado antes da entrega. Essas instruções são informações acionáveis que devem ser tratadas pelo funcionário da Contoso responsável pela embalagem.
+ **Informações não acionáveis** – por exemplo, um cliente visita a loja da Contoso e, durante sua conversa com uma associação da loja, expressa interesse nos *jogos Halo* e nos acessórios de jogos. O associado da loja anota essas informações. O mecanismo de recomendações do produto o utiliza para fazer recomendações ao cliente.

Em geral, as informações acionáveis são capturadas como *atividades* nos aplicativos de Finanças e Operações e nos aplicativos de engajamento do cliente. As informações não acionáveis são capturadas como *notas* nos aplicativos de Finanças e Operações e como *anotações* nos aplicativos de engajamento do cliente.

> [!TIP]
> Embora as notas sejam destinadas a informações não acionáveis, os aplicativos não impedem que você as utilize para armazenar e manipular informações acionáveis, caso queira usá-las dessa forma.

No momento, a Microsoft está lançando funcionalidades para a integração de notas. (A funcionalidade para a integração de atividades será liberada posteriormente). A integração da nota está disponível para clientes, fornecedores, ordens de venda e ordens de compra.

## <a name="create-a-note-in-a-customer-engagement-app"></a>Criar uma nota em um aplicativo de engajamento do cliente

Para criar uma nota em um aplicativo de engajamento do cliente e sincronizá-la com um aplicativo de Finanças e Operações, siga estas etapas.

1. No aplicativo engajamento do cliente, abra o registro da conta de um cliente.
2. No painel **Linha de tempo**, selecione o sinal de adição (**+**) e, em seguida, selecione **Nota** para criar uma nota.

    ![Criando uma nota em um aplicativo de engajamento do cliente.](media/notes-ce-1.png)

3. Informe um título e uma descrição e selecione **Adicionar nota**.

    ![Inserindo um título e uma descrição.](media/notes-ce-2.png)

    A nova nota é adicionada à linha do tempo do cliente.

    ![Nova nota na linha do tempo do cliente.](media/notes-ce-3.png)

4. Entre no aplicativo de Finanças e Operações e abra o mesmo registro de cliente. Lembre-se de que o botão **Anexos** (símbolo de clipe de papel) no canto superior direito indica que o registro tem um anexo.

    ![Notificação sobre um anexo.](media/notes-ce-4.png)

5. Selecione o botão **Anexos** para abrir a página **Anexos**. Você deve encontrar a nota criada no aplicativo de engajamento do cliente.

    ![Observação do aplicativo de engajamento do cliente.](media/notes-ce-5.png)

Todas as atualizações da nota são sincronizadas para frente e para trás entre o aplicativo de Finanças e Operações e o aplicativo de engajamento do cliente.

## <a name="create-a-note-in-a-finance-and-operations-app"></a>Crie uma nota em um aplicativo de Finanças e Operações

Também é possível criar uma nota em um aplicativo de Finanças e Operações e ela será sincronizada em um aplicativo de engajamento do cliente.

Para criar uma nota em um aplicativo de Finanças e Operações com um aplicativo de engajamento do cliente, siga estas etapas.

1. No aplicativo de Finanças e Operações, na página **Anexos**, selecione **Nova** \> **Nota**.

    ![Criando uma nota no aplicativo de Finanças e Operações.](media/notes-fo-1.png)

2. Insira um título e um breve conjunto de instruções e selecione **Salvar**.

    ![Inserindo um título e instruções.](media/notes-fo-2.png)

3. No aplicativo de engajamento do cliente, atualize o registro. Você deve encontrar a nova nota na linha do tempo.

    ![Nova nota na linha do tempo no aplicativo de engajamento do cliente.](media/notes-fo-3.png)

Você pode classificar uma nota como interna ou externa.

- No aplicativo de Finanças e Operações, na página **Anexos**, abra a nota e, em seguida, no campo **Restrição**, selecione **Interno** ou **Externo**.

    ![Campo de restrição.](media/notes-fo-4.png)

Você também pode cria uma URL.

1. No aplicativo de Finanças e Operações, na página **Anexos**, selecione **Nova** \> **URL**.
2. Insira um título e uma URL.
3. No campo **Restrição**, selecione **Interno** ou **Externo**.

    ![Criando uma URL no aplicativo de Finanças e Operações.](media/notes-fo-5.png)

4. Selecione **Salvar**.

    Como os aplicativos do engajamento do cliente não têm um tipo de URL, a URL é integrada com a gravação dupla como uma nota.

    ![URL aparecendo uma nota em um aplicativo de engajamento do cliente.](media/notes-ce-6.png)

> [!NOTE]
> Não há suporte para anexos de arquivo.

## <a name="templates"></a>Modelos

A integração da nota inclui um conjunto de mapas de tabelas que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

| Aplicativo de Finanças e Operações | Aplicativo Customer Engagement | Descrição |
|----------------------------|-------------------------|-------------|
| [Anexos do Cliente](mapping-reference.md#230) | Anotações | Empresas que usam texto sem formatação e URLs para capturar informações específicas do cliente (para organizações e pessoas). |
| [Anexos de documentos do fornecedor](mapping-reference.md#231) | Anotações | Empresas que usam texto sem formatação e URLs para capturar informações específicas do fornecedor (para organizações e pessoas). |
| [Anexos de documento de cabeçalho de ordem de venda](mapping-reference.md#229) | Anotações | Empresas que usam texto sem formatação e URLs para capturar informações específicas da ordem de venda. |
| [Anexos de documento de cabeçalho de ordem de compra](mapping-reference.md#232) | Anotações | Empresas que usam texto sem formatação e URLs para capturar informações específicas da ordem de compra. |

## <a name="limitations"></a>Limitações

Depois de instalar a solução de notas, não será possível desinstalá-la. 

Para obter mais informações, consulte [Referência de mapeamento de gravação dupla](mapping-reference.md).
