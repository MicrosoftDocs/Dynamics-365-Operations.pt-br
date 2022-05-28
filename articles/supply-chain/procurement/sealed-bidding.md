---
title: lances lacrados para RFQs
description: Este tópico descreve como configurar lances lacrados para manter as respostas de lance de fornecedor em segredo até que eles sejam abertos pela equipe de compra.
author: GalynaFedorova
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: dfc19646d6724627c8a25bcfc8a6b2a70a73c261
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675139"
---
# <a name="sealed-bidding-for-rfqs"></a>lances lacrados para RFQs

[!include [banner](../includes/banner.md)]

Os lances lacrados mantêm as respostas de lance de fornecedor em segredo até que eles sejam abertos pela equipe de compra. Todas as apostas relacionadas a uma solicitação de cotação (RFQ) estão disponíveis primeiro para serem abertas após a expiração do lance. Antes de um lance ser aberto, somente os usuários que têm funções de usuário dedicadas e que representam o fornecedor podem acessá-lo.

> [!IMPORTANT]
> A modificação ou a extensão de formulários, ou a criação de novos formulários ou lógicas comerciais pode vencer a proteção oferecida pela Microsoft para o lance lacrado. Você assume o risco de usar modificações, extensões, novos formulários ou lógica comercial ou a incapacidade de usar o recurso de lances lacrados devido a tais modificações, extensões, novos formulários ou lógica comercial.  A Microsoft não é responsável por danos decorrentes de modificações ou extensões de formulários, ou de novos formulários ou lógicas comerciais criados por você ou por terceiros para você. A Microsoft não oferece suporte técnico para modificações, extensões, novos formulários ou lógicas comerciais feitas por você ou por terceiros em seu nome. Você é o único responsável por cumprir todas as leis ou regulamentos aplicáveis sobre lances lacrados.

## <a name="how-bids-are-kept-secure"></a>Como os lances são mantidos em segurança

O lance lacrado usa a criptografia assimétrica para criptografar a chave de criptografia de lance (KEK) e a criptografia simétrica para criptografar o lance real. O sistema se integra ao Microsoft Azure Key Vault para gerar e gerenciar as chaves de criptografia usadas para criptografar os lances lacrados. Cada lance tem sua própria chave de criptografia. Essa criptografia é mantida em um key vault que pertence à organização que executa o Dynamics 365 Supply Chain Management. O sistema acessa o cofre de chaves sob demanda, sempre que a criptografia e a descriptografia forem necessárias.

## <a name="setup-and-configuration"></a>Instalação e configuração

Esta seção descreve os pré-requisitos que devem ser atendidos para que você possa enviar RFQs que exigem lances lacrados.

### <a name="step-1-set-up-user-access-to-sealed-bidding"></a>Etapa 1: configurar o acesso do usuário aos lances lacrados

Quando você usa lances lacrados, somente os usuários que estão definidos como a pessoa de contato de um fornecedor podem exibir, editar e enviar lances para esse fornecedor até que o período de lances expire. Esses usuários devem ter a função **Fornecedor (externa)** e devem ser definidos como uma pessoa de contato para a conta do fornecedor. A pessoa de contato também deve ter permissão para realizar colaboração entre fornecedores, conforme descrito em [Configurar e manter a colaboração entre fornecedores](set-up-maintain-vendor-collaboration.md).

Como os usuários que têm as permissões apropriadas e que estão configurados como contatos do fornecedor podem acessar os lances lacrados para um fornecedor, é importante controlar quem são esses usuários. O administrador do sistema que configura usuários e direitos de acesso é responsável por limitar o acesso a lances lacrados aos usuários que realmente têm permissão para exibi-los.

### <a name="step-2-enable-the-sealed-bidding-feature"></a>Etapa 2: habilitar o recurso de lances lacrados

Para começar a configurar ou usar este recurso, você deve verificar se ele está disponível no seu sistema. Os administradores podem usar o espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Tarefas de compras e fornecimento*
- **Nome do recurso:** *lances lacrados para RFQ*

### <a name="step-3-set-up-azure-key-vault"></a>Etapa 3: configurar o Azure Key Vault

O Supply Chain Management usa chaves de criptografia para proteger todos os lances lacrados e mantê-los secretos até o momento apropriado. Ele aproveita os recursos do Key Vault para gerar e gerenciar as chaves necessárias. Portanto, você deve configurar uma conexão do Supply Chain Management para um key vault para habilitar o sistema.

> [!IMPORTANT]
> Os cofres de chaves usados para lances lacrados devem atender aos seguintes requisitos:
>
> - Se você usar uma área restrita para desenvolvimento e teste, será necessário ter um cofre de chaves dedicado para a área restrita e outro para produção.
> - Cada cofre de chaves deve ser criado em uma assinatura do Azure pertencente à sua organização (não na assinatura em que você está executando o Supply Chain Management).
> - Cada cofre de chaves deve ser usado exclusivamente para lances lacrados. Não use os cofres de chaves de lances lacrados para qualquer outra finalidade.

Cada lance recupera sua própria chave secreta. Essa chave é usada toda vez que um usuário exibe, atualiza ou abre o lance.

O Key Vault gera a chave usada para recuperar o segredo quando o fornecedor seleciona **Lance** na interface de colaboração entre fornecedores. A chave expira depois de um tempo fixo que o gerente de compras define na página **Parâmetros de aquisição e fornecimento** no Supply Chain Management. Depois que a chave expirar, ninguém poderá exibir, editar ou abrir o lance. Portanto, é importante configurar a expiração de chave para que haja tempo suficiente para que o processo de lances seja concluído.

Nas próximas três etapas, você configurará a conexão com o Key Vault. Primeiro, você vai configurar um cofre de chaves para usar com lances lacrados. Em seguida, você vai configurar o Supply Chain Management para se comunicar com o cofre de chaves. Por fim, você definirá a hora de vencimento da chave.

### <a name="step-4-set-up-a-key-vault-to-use-with-sealed-bidding"></a>Etapa 4: configurar um cofre de chaves para usar com lances lacrados

Para configurar seu cofre de chaves, siga estas etapas. A ordem das etapas é importante.

1. Se você ainda não configurou uma assinatura do Azure separada da subscrição em que está executando Supply Chain Management, configure-a.
1. Configure um cofre de chaves no seu armazenamento separado do Azure. Para obter mais informações, consulte [Manter o armazenamento do Azure Key Vault](https://support.microsoft.com/help/4040294/maintaining-azure-key-vault-storage).
1. Configure o aplicativo do Supply Chain Management para que funcione como um cliente para o seu cofre de chaves. Para obter mais informações, consulte [Configurar o cliente do armazenamento do Azure Key Vault](https://support.microsoft.com/help/4040305/setting-up-azure-key-vault-client).

### <a name="step-5-configure-key-vault-parameters-in-supply-chain-management"></a>Etapa 5: configurar parâmetros do Key Vault no Supply Chain Management

Para configurar o Supply Chain Management para se comunicar com o cofre de chaves durante os lances lacrados, siga estas etapas.

1. Entre no Supply Chain Management e Acesse **Administração do sistema \> Configuração \> Parâmetros do Key Vault**.
1. Selecione **Novo** para criar um registro e defina os seguintes campos para ele:

    - **Nome** - Digite um nome.
    - **Descrição** - Digite uma descrição.
    - **URL do cofre de chaves** – Insira a URL padrão do seu cofre de chaves.
    - **Cliente do Key Vault** – Insira a ID do cliente interativo do aplicativo do Active Directory associado a um cofre de chaves para autenticação.
    - **Chave secreta do Key Vault** – Insira a referência secreta para o certificado.
    - **Habilitado para lances lacrados** – Defina esta opção como *Sim*.

![Página parâmetros do Key Vault](media/sealed-bidding-key-vault-param.png "Página parâmetros do Key Vault")

> [!NOTE]
> Você pode habilitar somente uma configuração do Key Vault para lances lacrados por vez. Antes de desabilitar uma configuração de cofre de chaves existente, você deve verificar se todos os lances lacrados que o usam estão abertos. Inspecione todos os casos de RFQ do tipo *Lacrado* e verifique se todas as respostas para ele estão reveladas.

### <a name="step-6-set-the-key-expiration-time"></a>Etapa 6: definir a hora de vencimento da chave

Para definir a hora de vencimento aplicada à chave gerada para cada novo lance, siga estas etapas.

1. Acesse **Parâmetros de compras e fornecimento \> Configuração \> Parâmetros de compras e fornecimento**.
1. Na guia **Solicitação de cotação**, no campo **Compensação de dias**, insira o número de dias que o período de RFQ deve durar. Quando uma RFQ é criada, o número de dias que você insere aqui é adicionado à data do sistema para definir a data de validade padrão da RFQ.
1. No campo **Compensação em dias da chave de criptografia**, insira o número de dias em que cada chave de criptografia deve ser válida após sua emissão. Depois que a chave de criptografia expirar, ninguém poderá exibir, editar ou abrir o lance lacrado que a usa.

> [!TIP]
> O valor do campo **Compensação de dias da chave de criptografia** não pode ser menor do que o valor do **Compensação de dias da chave de criptografia**.

### <a name="step-7-set-the-default-bid-type"></a><a name="set-default-bid-type"></a>Etapa 7: definir o tipo de lance padrão

Cada caso de RFQ tem um tipo de lance. O tipo de lance define se esse caso de RFQ oferece cotação aberta ou lacrada.

#### <a name="rfq-cases-that-dont-have-a-solicitation-type"></a>Casos de RFQ que não têm um tipo de solicitação

Para definir o tipo de lance padrão atribuído a novos casos de RFQ que não são atribuídos a um tipo de solicitação quando eles são criados, siga estas etapas.

1. Acesse **Parâmetros de compras e fornecimento \> Configuração \> Parâmetros de compras e fornecimento**.
1. Na guia **Solicitação de cotação**, defina o campo **Tipo de lance** como *Lacrado*.

#### <a name="rfq-cases-that-have-a-solicitation-type"></a>Casos de RFQ que têm um tipo de solicitação

Para definir o tipo de lance padrão atribuído a novos casos de RFQ que são atribuídos a um tipo de solicitação quando eles são criados, siga estas etapas.

1. Acesse **Aquisição e fornecimento \> Configuração \> Solicitação de cotação \> Tipo de solicitação**.
1. Crie um novo tipo de solicitação ou selecione um tipo de solicitação existente no qual você deseja usar um tipo de lance *Lacrado*.
1. Defina o campo **Tipo de lance** como *Lacrado*.
1. Repita essas etapas para cada tipo de solicitação adicional em que você deseja implementar o lance lacrado.

> [!TIP]
> Um tipo de solicitação não precisa ser atribuído quando uma nova RFQ é criada. Se um tipo de solicitação for atribuído, o tipo de lance padrão de uma RFQ poderá recuperá-lo. Caso contrário, será possível usar o tipo de solicitação padrão definido nos Parâmetros de aquisição e fornecimento.

## <a name="the-sealed-bidding-process"></a>O processo de lances lacrados

Os lances lacrados seguem quase o mesmo processo descrito em [Visão geral de solicitações de cotação (RFQs)](request-quotations.md). A principal diferença é que os dados de lance e seus anexos são mantidos criptografados até que o lance seja aberto.

> [!IMPORTANT]
> [Questionários](/dynamicsax-2012/appuser-itpro/view-and-respond-to-questionnaires) não são criptografados e não devem ser usados para coletar informações confidenciais

Aqui está uma descrição do processo:

1. Você cria e envia uma RFQ a um ou mais fornecedores.
1. Os fornecedores respondem enviando seu lance lacrado.
1. Você deslacra os lances depois da data de vencimento da entrada do lance.
1. Os lances tornam-se visíveis e você pode avaliá-los e compará-los.
1. Depois que um lance é aceito, você gera uma ordem de compra, gera um contrato de compra ou atualiza uma requisição de compra.

### <a name="create-an-rfq-case-that-uses-sealed-bidding"></a>Criar um caso de RFQ que use lances lacrados

O processo de criação de um caso de RFQ para lances lacrados é quase igual ao processo para lances não lacrados. Para obter informações sobre como criar os dois tipos de ocorrências de RFQ, consulte [Criar uma solicitação de cotação](tasks/create-request-quotation.md). Esta seção destaca algumas considerações importantes ao criar uma RFQ para lances lacrados.

As ocorrências de RFQ para lances lacrados devem ter um valor **Tipo de lance** de *Lacrado*. Há três maneiras de atribuir esse valor a um caso de RFQ:

- Defina o valor diretamente no caso de RFQ após criá-lo.
- Defina o lance lacrado como o tipo de lance padrão para todos os casos de RFQ nos Parâmetros de aquisição e fornecimento. (Consulte a seção [Definir o tipo de lance padrão](#set-default-bid-type) anteriormente neste tópico.)
- Ao criar um novo caso de RFQ, selecione um tipo de solicitação que esteja configurado para lances lacrados. (Consulte a seção [Definir o tipo de lance padrão](#set-default-bid-type).)

Em lances lacrados, o valor **Data e hora de vencimento** do caso de RFQ estabelece quando os lances enviados podem ser abertos. O valor **Data e hora de vencimento** em cada linha corresponderão ao valor no cabeçalho.

Não é possível alterar o tipo de lance depois que um caso de RFQ é enviado.

### <a name="vendors-respond-to-an-rfq"></a>Fornecedores respondem a uma RFQ

Os fornecedores que respondem a um lance lacrado usam o mesmo procedimento que é usado para responder a lances abertos, conforme destacado em [Trabalhar com as RFQs no espaço de trabalho de cotação do fornecedor](vendor-collaboration-work-customers-dynamics-365-operations.md#working-with-rfqs-in-the-vendor-bidding-workspace). Para obter instruções detalhadas sobre como trabalhar com lances abertos e lances lacrados, consulte [Inserir e comparar ofertas de RFQ e contratos de premiação](tasks/enter-compare-rfq-bids-award-contracts.md). A única diferença entre o processamento de lances lacrados e lances abertos é que, até o período de lances expirar, os profissionais de compras não podem abrir o lance lacrado de um fornecedor. Somente uma pessoa de contato para o fornecedor pode abrir o lance lacrado do fornecedor.

> [!IMPORTANT]
> Em lances lacrados, os fornecedores podem carregar os anexos somente no formato PDF. Nenhum outro formato será aceito.

Depois que um usuário de fornecedor registrado seleciona um **Lance** em uma RFQ de lance lacrado, ele poderá inserir seus dados de lance e esses dados serão mantidos em segurança. Os fornecedores podem salvar seu trabalho enquanto preparam um lance, retornar a ele sempre que necessário e depois enviá-lo quando estiver pronto. Os fornecedores também podem exibir sues lances depois de enviá-los. Se os fornecedores precisarem alterar seus lances depois de o enviarem, poderão retomá-lo, atualizá-lo e reenviá-lo a qualquer momento até o período de lances expirar.

As seguintes condições se aplicam durante o lance lacrado:

- Durante o lance lacrado, o sistema cria um diário de *Solicitações de cotação*.
- Quando um fornecedor envia um lance, os diários de RFQ sem linhas são criados com um preço lacrado.
- Depois que o caso é aberto, os diários de RFQ são criados com preço e valor. Você pode acessar este diário selecionando **Diários de solicitação de cotação** na página **Todas as solicitações de cotação**.
- O sistema armazena um log de cada ação que os usuários executam em um lance lacrado. Essas ações incluem exibição, edição e salvamento do lance. Esse log é visível para o fornecedor e para os profissionais de compras que têm acesso ao lance.
- À medida que o lance progride, os profissionais de aquisição podem exibir seu status. Em seguida, o status será *Fornecedor está atualizando* ou *Enviado pelo fornecedor*.
- O status das linhas em um lance lacrado permanece como *Enviado* até que o lance seja aberto.
- Se o fornecedor optar por recusar um lance, esse lance terá um status **Andamento da resposta** de *Recusado pelo fornecedor*. Este status será visível para a equipe de compras.
- As respostas em questionários **não** são armazenadas no formulário criptografado no banco de dados. Portanto, elas não são lacradas. No entanto, elas não estarão visíveis na interface de usuário de RFQ até que o caso seja aberto.

### <a name="all-sealed-bid-activities-are-logged"></a>Todas as atividades de lance lacrado são registradas

Um log detalhado registra todas as atividades e ações do usuário em um lacre. O registro de atividades permite que as organizações determinem quem atualizou um lance durante seu ciclo de vida e quais foram as atualizações. Ele também permite que as empresas confirmem que somente as pessoas autorizadas acessaram um lance lacrado. O registro de atividades está disponível em todas as páginas de **Atividades** de lance.

### <a name="review-rfq-activity"></a>Analisar atividade de RFQ

Cada interação com o lance é registrado e pode ser exibida na página **Atividade**. A ilustração a seguir mostra um exemplo.

![Exemplo da página Atividade](media/sealed-bidding-rfq-activity.png "Exemplo da página Atividade")

Os fornecedores podem acessar a página **Atividade** selecionando **Atividade** na página **Lance lacrado da solicitação de cotação**. A equipe de aquisição pode acessá-lo selecionando **Atividade** na página **Solicitação de cotação**. O registro de atividades oferece visibilidade total para fornecedores e para a equipe de aquisição que acessou o lance. Portanto, ele pode revelar qualquer acesso não autorizado.

### <a name="unseal-sealed-bids"></a>Abrir lances lacrados

Quando o valor **Data e hora de vencimento** que foi configurado para um caso de RFQ de lance lacrado passar, o botão **Abrir** se tornará disponível. Selecione **Abrir** para abrir todos os lances para o caso de RFQ selecionado. Todos os dados de lance e anexos ficam visíveis para que as respostas ao caso possam ser gerenciadas. Além disso, são criados diários que contêm os dados de lance enviados.

O evento de abertura é registrado e pode ser exibido na página **Atividade**.

### <a name="process-accepted-bids"></a>Processar lances aceitos

O processo de comparação e aprovação de lances previamente lacrados é o mesmo que o processo para lances abertos. Para obter informações sobre como pontuar, comparar, rejeitar e aceitar lances abertos, consulte [Inserir e comparar lances de RFQ e contratos de premiação](tasks/enter-compare-rfq-bids-award-contracts.md).

## <a name="the-rfq-activity-log-can-never-be-deleted"></a>O registro de atividade de RFQ nunca pode ser excluído

Ninguém, nem mesmo os administradores e o suporte da Microsoft, podem editar ou excluir o registro de atividades da RFQ. Essa restrição ajuda a garantir a imparcialidade do processo de lances lacrados. Isso também ajuda a garantir que uma trilha de auditoria precisa seja mantida.
