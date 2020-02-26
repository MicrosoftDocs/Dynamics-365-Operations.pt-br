---
title: Configurar contas de fornecedor
description: Este tópico descreve os tipos de informações que você deve especificar quando cria uma nova conta de fornecedor.
author: mkirknel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: smmContactPerson, VendBankAccounts, VendTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 191053
ms.assetid: 06168199-7c54-40e9-a038-4eb274ca958d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63843381207fbe6cb72ac1b5533eda754b1ba55b
ms.sourcegitcommit: 5457cbec3399d8ed9f87c3a9dc586173b5616c11
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3012436"
---
# <a name="set-up-vendor-accounts"></a>Configurar contas de fornecedor

[!include [banner](../includes/banner.md)]

Este tópico descreve os tipos de informações que você deve especificar quando cria uma nova conta de fornecedor.

Ao criar uma conta de fornecedor, insira informações sobre o fornecedor. Essas informações são usadas para inserir dados automaticamente nos documentos e rastrear as atividades que envolvem o fornecedor. Por exemplo, você pode configurar as seguintes informações para um fornecedor:

-   Atribuir um grupo de fornecedores. Cada fornecedor deve ser atribuído a um grupo de fornecedores. Os fornecedores em um grupo de fornecedores têm parâmetros em comum. Por exemplo, eles podem ter as mesmas condições de pagamento.
-   Configurar o fornecedor para importação de catálogo. Os fornecedores podem fornecer um arquivo que contenha o catálogo de seus itens e serviços. Esse arquivo pode ser carregado para que os funcionários possam solicitar itens ou serviços do fornecedor.
-   Atribuir o fornecedor às categorias de compras.
-   Permitir a um fornecedor existente fazer negócios com outra entidade legal na organização.
-   Colocar um fornecedor em espera para tipos específicos de transações.
-   Configure as informações bancárias do fornecedor, de modo que seja possível enviar pagamentos eletronicamente.
-   Configurar informações sobre imposto, entrega, fatura e pagamento para o fornecedor. Por padrão, essas configurações são copiadas em novos documentos que você cria para o fornecedor.
-   Configurar as dimensões financeiras padrão usadas para lançar transações automaticamente com o fornecedor nas contas financeiras.

Para agilizar o processo de criação de contas de fornecedor, você pode criar modelos. Para criar um modelo, na página **Fornecedor**, no painel de ação, clique em **Opções** &gt; **Informações sobre registro**. Em seguida, clique em **Modelo de contas da empresa**. Os modelos de contas da empresa são compartilhados com outros usuários.  

Você também pode criar um modelo de usuário para seu próprio uso. Você não pode excluir um fornecedor associado com outros registros, como contatos ou produto.

## <a name="vendor-account-numbers"></a>Números de conta do fornecedor
O número de conta é um identificador exclusivo de um fornecedor. Você pode configurar números de conta para que sejam gerados automaticamente durante a criação de um fornecedor. Também é possível configurar a sequência numérica de modo que os números de conta sejam inseridos manualmente. Por exemplo, talvez você queira usar o número de telefone do fornecedor como identificador.

## <a name="vendor-organizations-and-individual-vendors"></a>Organizações de fornecedor e fornecedores individuais
Ao criar uma nova conta de fornecedor, especifique se o fornecedor é uma organização ou uma pessoa. Sua seleção afeta as informações que você deve preencher para o fornecedor. Para uma pessoa, essas informações incluem o nome, o sobrenome e o cargo. Para uma organização, essas informações incluem o número da organização e o número de funcionários.

## <a name="addresses"></a>Endereços
Para cada fornecedor, você pode definir vários endereços, sendo cada um deles usado para uma finalidade diferente. Por exemplo, você pode criar um endereço que tenha **Fatura** como finalidade. Ou, se você pretende pagar o fornecedor por meio de cheques, poderá configurar um endereço que tenha **Remeter para** como finalidade. Se você precisar especificar um endereço a ser usado em transferências de dinheiro para bancos estrangeiros, a finalidade será **SWIFT**.

## <a name="vendor-contacts"></a>Contatos de fornecedor
Você pode armazenar os contatos de um fornecedor. Esses contatos poderão, então, ser usados em documentos como ordens de compra ou RFQs (solicitações de cotação).  

Para adicionar contatos a um fornecedor, na página **Todos os fornecedores**, na guia **Fornecedor**, no grupo **Configurar**, clique em **Contatos** &gt; **Adicionar contatos**.  

Você pode criar contatos de fornecedor a partir do zero. Se desejar, você pode copiar detalhes de outra pessoa que já esteja registrada no Supply Chain Management e editar as informações conforme necessário.  

**Observação:** adicionar um contato de um fornecedor não é o mesmo que adicionar informações de contato desse fornecedor. Embora você possa adicionar informações de contato gerais de um fornecedor, também é possível ter várias pessoas específicas que são contatos nessa empresa e que têm suas próprias informações de contato.  

Você não poderá excluir um registro pessoal de contato quando o contato for referenciado em um documento. Em vez disso, poderá desativar o contato.  

Você pode adicionar contatos de fornecedor a seus contatos pessoais no Microsoft Office 365. Entretanto, primeiro configure a sincronização entre o Supply Chain Management e o Office 365 na sincronização do Microsoft Exchange Server e no assistente de instalação do Microsoft Outlook.

## <a name="vendors-in-different-legal-entities"></a>Fornecedores em entidades legais diferentes
Se um fornecedor estiver registrado para apenas uma entidade legal em sua organização, e outras entidades legais precisarem registrar o mesmo fornecedor, use a página **Adicionar fornecedor a outra entidade legal** para configurar o fornecedor de modo que ele faça negócios com outra entidade legal. Você deve selecionar um grupo de fornecedores, uma moeda e um status de suspensão para o fornecedor na entidade legal selecionada.  

Se várias entidades legais na organização fizerem negócios com o mesmo fornecedor e cada uma mantiver uma conta separada para esse fornecedor, você poderá mesclar as IDs do participante para as contas de fornecedor. Assim, informações como endereço e número de funcionários podem ser compartilhadas para que você as atualize em um único local.  

Para mesclar IDs de participantes, sigas as etapas a seguir.

1.  Na página **Catálogo de endereços global**, selecione os registros de catálogo de endereços que representam o fornecedor em cada entidade legal a ser incluída no mapeamento.
2.  No Painel de Ações, clique em **Mesclar registros**.

## <a name="agreements"></a>Contratos
Ao configurar uma conta de fornecedor, talvez você queira registrar os contratos que firmou com o fornecedor. Você pode configurar contratos de preço e desconto usando as ações no registro do fornecedor. Você também pode configurar um contrato de compra na página **Contratos de compra**.

## <a name="putting-a-vendor-on-hold"></a>Colocando um fornecedor em espera
Você pode colocar um fornecedor em espera em vários tipos de transação. As opções a seguir estão disponíveis:

-   **Não** – Não há nenhuma suspensão para o fornecedor.
-   **Fatura** – Nenhuma fatura pode ser postada para o fornecedor.
-   **Tudo** – O fornecedor está em espera em todos os tipos de transação. Esses tipos de transações incluem requisições de compra, faturas e pagamentos.
-   **Pagamento** – Nenhum pagamento pode ser gerado para o fornecedor.
-   **Requisição:** – as requisições de compra não podem ser criadas para o fornecedor, e as linhas de requisição que foram criadas antes que o fornecedor fosse definido como "em espera" não podem ser convertidas em uma ordem de compra. As linhas de requisição para o fornecedor serão canceladas se a sua política estiver definida para criar ordens de compra automaticamente.
-   **Nunca** – O fornecedor nunca é colocado em espera por inatividade.

Quando você colocar um fornecedor em espera, também poderá especificar um motivo e uma data em que o status de suspensão será encerrado. Se você não inserir uma data final, o status de suspensão do fornecedor terá duração indeterminada.

Você pode atualizar em massa o status Em espera **Tudo** para os fornecedores com base nos critérios selecionados na página **Desativação de fornecedor**, e atribuir um motivo pelo qual o fornecedor está Em espera.

Os seguintes critérios são usados para incluir fornecedores que foram desativados em um período, para incluir ou excluir fornecedores que são funcionários, e para excluir os fornecedores em um período de carência antes da próxima suspensão.

- Com base no número de dias inserido no campo **No período de atividade** na página **Desativação de fornecedor**, o aplicativo calcula a última data em que o fornecedor pode ter qualquer atividade seja considerada inativa. Ou seja, a data atual menos o número de dias inserido. Se houver uma ou mais faturas existentes para o fornecedor onde a data é posterior à última data calculada, o fornecedor será excluído da desativação. Isto também será validado se o fornecedor tiver pagamentos após essa data, requisições de compra em aberto, ordens de compra abertas, solicitações de cotações ou respostas.
- O número de dias no campo **Período de carência antes da próxima suspensão** é usado para calcular a última data de carência. Ou seja, a data atual menos os dias inseridos. Isso só se aplica aos fornecedores que foram desativados anteriormente. No caso de uma desativação anterior, o aplicativo verifica o histórico de outras ocorrências de desativação para o fornecedor e verifica se última desativação ocorreu antes da última data de carência. Se isso ocorrer, o fornecedor será incluído no processo de desativação.
- O parâmetro **Incluir funcionários** refere-se aos fornecedores que estão vinculados a um funcionário. É possível definir se você deseja incluir tais funcionários.

Este processo excluirá sempre os fornecedores que tiverem no campo **Fornecedor suspenso** o valor **Nunca**.

Os fornecedores que passarem nas validações são colocados em espera, o que define o campo **Fornecedor suspenso** como **Tudo** e o **Motivo** pelo qual foi selecionado. Um registro no histórico Em Espera é criado para o fornecedor.

## <a name="vendor-invoice-account"></a>Conta de fatura de fornecedor
Se mais de um fornecedor tiver o mesmo endereço de cobrança ou se um fornecedor for faturado por meio de um terceiro, você poderá especificar uma conta de fatura no registro do fornecedor. A conta de fatura é a conta na qual o valor da fatura será creditado quando você criar uma fatura de fornecedor a partir de uma ordem de compra. Se você não inserir uma conta de fatura no registro do fornecedor, a conta do fornecedor será usada como conta de fatura.

## <a name="vendor-bank-accounts"></a>Contas bancárias do fornecedor
Se você precisar fazer pagamentos para uma conta bancária de fornecedor, poderá inserir informações sobre o banco e as contas bancárias do fornecedor na página **Contas bancárias de fornecedor**. Você também pode inserir informações sobre validação e pagamentos relacionados à conta bancária. Por exemplo, você pode adicionar pré-registos às contas bancárias de fornecedores. Esses pré-registros podem ser usados para verificar a precisão dos dados da conta, como números de roteiro e números de conta. Você deve especificar uma conta padrão para pagamentos ao fornecedor. Porém, quando você faz um pagamento real, é possível alterar essa conta para uma das outras contas do fornecedor.

## <a name="ledger-accounts"></a>Contas contábeis
Você pode especificar as contas padrão que aparecerão automaticamente nos diários de fatura do fornecedor especificado. Essa funcionalidade poderá ser útil se você normalmente pagar pelos mesmos tipos de itens ou serviços dos mesmos fornecedores ao longo do tempo. Ao especificar uma conta padrão, você poderá inserir entradas no diário de fatura com rapidez e eficiência. As contas padrão que você especificar não são usadas para ordens de compra, ou para faturas de fornecedor inseridas na página **Fatura de fornecedor**.  

Selecione contas padrão na página **Configuração de conta padrão**, que você pode abrir na guia **Fatura** no registro de fornecedor. As contas selecionadas aqui aparecem na lista de contas filtrada para a conta de fornecedor quando você insere uma entrada de diário. Você pode definir uma das contas como conta padrão.



