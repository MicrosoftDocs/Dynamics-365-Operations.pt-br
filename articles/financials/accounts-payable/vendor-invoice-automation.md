---
title: Automação das faturas dos fornecedores
description: Este tópico explica os recursos disponíveis para a automação ponta a ponta de notas fiscais de fornecedor, até mesmo notas fiscais que incluem anexos.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e81822294c86961137ff649be1f219b896cbc10c
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2019
ms.locfileid: "896571"
---
# <a name="vendor-invoice-automation"></a>Automação das faturas dos fornecedores

[!include [banner](../includes/banner.md)]

Este tópico explica os recursos disponíveis para a automação ponta a ponta de notas fiscais de fornecedor, até mesmo notas fiscais que incluem anexos.

As organizações que desejam agilizar seus processos de Contas a Pagar (AP) geralmente identificam o processamento da fatura como uma das principais áreas de processo que devem ser mais eficientes. Em muitos casos, essas organizações descarregam o processamento de faturas em papel para um provedor de serviços de reconhecimento óptico de caracteres (OCR) de terceiros. Eles então recebem metadados de fatura legíveis por máquina, juntamente com uma imagem digitalizada de cada fatura. Para ajudar com a automação, uma solução de "última milha" foi construída para permitir o consumo desses artefatos no sistema de faturamento. O Microsoft Dynamics 365 for Finance and Operations agora habilita esta automação de "última milha" imediatamente, por meio de uma solução de automação de fatura.

## <a name="solution-context"></a>Contexto da solução

A solução de automação de fatura permite uma interface padrão que pode aceitar metadados de fatura para o cabeçalho da fatura e linhas de fatura, e também os anexos aplicáveis ​​à fatura. Qualquer sistema externo que possa gerar artefatos que cumpram esta interface poderá enviar o feed para Finanças e Operações para o processamento automático de faturas e anexos.

A ilustração a seguir mostra um exemplo de cenário de integração onde a Contoso se associou com um provedor de serviços de OCR para processamento de fatura de fornecedor. Os fornecedores da Contoso enviam faturas ao provedor de serviços por e-mail. Através do processamento de OCR, o provedor de serviços gera metadados de fatura (cabeçalho e/ou linhas) e uma imagem digitalizada da fatura. Uma camada de integração transforma esses artefatos para que Finanças e Operações possam consumi-los.

![Cenário de integração de amostra](media/vendor_invoice_automation_01.png)

Várias variações do cenário anterior são possíveis se a integração da fatura for necessária. A migração de dados é outro caso de uso em que esta interface pode ser usada para criar faturas e anexos no Finance and Operations.

### <a name="solution-components"></a>Componentes da solução

A pegada de solução consiste nos seguintes componentes:

+ Entidades de dados para o cabeçalho da fatura, linhas de fatura e anexos de fatura
+ Processamento de exceção para faturas
+ Um visualizador de anexo lado a lado nas faturas

O restante deste tópico fornece descrições detalhadas desses componentes da solução.

## <a name="data-entities"></a>Entidades de dados

Um pacote de dados é a unidade de trabalho que deve ser enviada para Finanças e Operações, de modo que cabeçalhos de fatura, linhas de fatura e anexos de fatura possam ser criados. As seguintes entidades de dados são usadas para os artefatos que compõem o pacote de dados:

+ Cabeçalho da fatura de fornecedor
+ Linha de fatura de fornecedor
+ Anexo de documento de fatura de fornecedor

O anexo do documento de fatura do fornecedor é uma nova entidade de dados que é introduzida como parte desse recurso. A entidade do cabeçalho da fatura de fornecedor foi modificada para que ele suporte anexos. A entidade da linha de fatura do fornecedor não foi modificada para esse recurso.

Este tópico não fornece uma definição detalhada de um pacote de dados. Também não explica como criar pacotes de dados. Para essa informações, consulte [Estrutura entidades de dados e pacotes](../../dev-itpro/data-entities/data-entities-data-packages.md).

Para gerar rapidamente dados de teste que incluem faturas e anexos, siga estas etapas.

1. Faça login na sua instância do Finance and Operations.
1. Vá para **Contas a pagar** > **Faturas** > **Faturas de fornecedor em aberto**.
1. Crie faturas com linhas e anexos.

    > [!NOTE]
    > Os anexos devem ser anexos de cabeçalho. Atualmente, a entidade de anexo de documento de fatura de fornecedor não suporta anexos de linha.

1. Abra o espaço de trabalho **Gerenciamento de dados**.
1. Crie um trabalho de exportação que inclua o cabeçalho da fatura de fornecedor, a linha da fatura de fornecedor e as entidades de anexo do documento de fatura de fornecedor.
1. Exporte os dados.
1. Baixe os dados exportados na forma de pacote. Agora você pode usar o pacote para importar dados em instâncias de destino para fins de teste.

### <a name="determining-the-legal-entity-for-an-invoice"></a>Determinar a entidade legal para uma fatura

As faturas que são importadas através de pacotes de dados podem ser associadas à entidade legal à qual pertencem de duas maneiras:

+ O trabalho de importação que processa a fatura importa-a para a mesma empresa em que o trabalho estava agendado no espaço de trabalho **Gerenciamento de dados**. Em outras palavras, a empresa do trabalho determina a empresa à qual a fatura pertence.
+ Quando o pacote de dados que contém as faturas é enviado para Finanças e Operações, o solicitante (ou seja, o aplicativo de integração que funciona fora do Finance and Operations) pode mencionar explicitamente a ID da empresa na solicitação HTTP. Nesse caso, o contexto da empresa em que o trabalho de processamento é executado no Finance and Operations é substituído e as faturas são importadas para a empresa que foi passada através da solicitação HTTP.

> [!NOTE]
> Esse comportamento é um comportamento padrão de gerenciamento de dados. É explicado aqui, no contexto das faturas, apenas por uma questão de exaustividade.

## <a name="exception-processing"></a>Processamento de exceções

Nos cenários em que as faturas dos fornecedores entram no Finance and Operations por meio da integração, deve haver uma maneira fácil para um membro da equipe de contas a pagar processar exceções ou faturas que falharam e criar faturas pendentes fora das faturas que falharam. Esse processamento de exceção para faturas de fornecedores agora é parte do Finance and Operations.

### <a name="exceptions-list-page"></a>Página da lista de exceções

A página da lista nova para exceções de fatura está disponível em **Contas a pagar** > **Faturas** > **Importar falhas** > **Faturas de fornecedor que falharam na importação**. Esta página mostra todos os registros de cabeçalho da fatura de fornecedor na tabela de teste da entidade de dados do cabeçalho da fatura de fornecedor. Observe que você pode visualizar os mesmos registros no espaço de trabalho **Gerenciamento de dados** onde você também pode executar as mesmas ações que são fornecidas no recurso de tratamento de exceção. No entanto, a UI que o recurso de tratamento de exceção fornece é otimizada para um usuário funcional.

![Página da lista de exceções](media/vendor_invoice_automation_02.png)

Esta página da lista inclui os seguintes campos que entram através do feed:

+ **Empresa** – A empresa à qual a fatura pertence
+ **Mensagem de erro** – A mensagem de erro que a estrutura de gerenciamento de dados envolve para explicar por que a fatura não pôde ser criada
+ **Número** – O número da fatura
+ **Conta de fatura**
+ **Nome** – O nome do fornecedor
+ **Conta de fornecedor**
+ **Ordem de compra** – O número da ordem de compra (OC) da fatura
+ **Data do lançamento**
+ **Data da fatura**
+ **Descrição da fatura**
+ **Moeda**
+ **Registro**
+ **Referência de linha** – O identificador proveniente do sistema externo

    > [!NOTE]
    > A linha de referência não é o ID de fatura.

Esta página da lista também possui um painel de visualização que você pode usar das seguintes maneiras:

+ Veja toda a mensagem de erro, para que não seja necessário expandir a coluna **Mensagem de erro** na grade.
+ Exiba toda a lista de anexos para a fatura, se algum anexo tiver sido fornecido com a fatura.

A página da lista suporta as seguintes ações:

+ **Editar** – Abra a gravação de exceção no modo de edição, para que você possa resolver os problemas.
+ **Opções** – Acessar opções padrão disponíveis em páginas de listagem. Você pode usar a opção **Adicionar ao espaço de trabalho** para inserir a página da lista de exceções em seu espaço de trabalho como uma lista ou bloco.

### <a name="exception-details-page"></a>Página de detalhes de exceção

Quando você inicia o modo de edição, aparece a página de detalhes da exceção da fatura com problemas. Se houver anexos, a fatura e o anexo padrão aparecem lado a lado na página de detalhes da exceção.

![Página de detalhes de exceção](media/vendor_invoice_automation_03.png)

Na ilustração anterior, não havia nenhuma linha para o cabeçalho da fatura de fornecedor que entrou. Portanto, a seção de linhas está vazia.

A página de detalhes da exceção suporta a seguinte operação:

+ **Criar fatura em aberto** – Depois de corrigir os problemas na fatura como parte do processamento de exceções, você pode clicar neste botão para criar a fatura pendente. A criação de faturas em aberto ocorre em segundo plano (como uma operação assíncrona).

### <a name="shared-service-vs-organization-based-exception-processing"></a>Serviço compartilhado versus processamento de exceções baseado em organização

A página da lista de exceções suporta as construções de segurança padrão que a área de trabalho **Gerenciamento de dados** suporta para processamento dos registros de preparo. O trabalho de importação de fatura pode ser protegido das seguintes maneiras:

+ Por função de usuário
+ Por usuário
+ Por entidade legal

![Trabalho de importação garantido por função de usuário e entidade legal](media/vendor_invoice_automation_04.png)

Se a segurança estiver configurada para o trabalho de importação de fatura, a página da lista de exceções estará de acordo com essas configurações. Os usuários poderão ver apenas os registros de exceções de fatura que esta configuração permite ver.

Por exemplo, a Contoso decidiu processar exceções de fatura por entidade legal. Portanto, a segurança é configurada no trabalho de importação de fatura de tal forma que um usuário na entidade legal A pode ver apenas exceções de fatura na entidade legal A, enquanto um usuário na entidade legal B pode ver apenas exceções de fatura na entidade legal B. Esta configuração permite a segregação de funções para a gestão de exceções de fatura.

A Contoso também pode decidir não aplicar qualquer segurança, de modo que os mesmos usuários possam processar exceções de faturamento para todas as entidades legais. Essa configuração permite um cenário de serviços compartilhados para o gerenciamento de exceções de fatura.

## <a name="side-by-side-attachment-viewer"></a>Visualizador de anexo lado a lado

Para ajudá-lo a visualizar facilmente os anexos para as faturas de fornecedor, as seguintes páginas que são usadas no processo de faturamento agora fornecem um visualizador de anexos:

+ **Manuseio de exceção**
+ Página **Faturas de fornecedor em aberto** (também disponível no processo de revisão de fatura)
+ Página de consulta **Diário de fatura** (para as faturas lançadas)

Veja aqui a funcionalidade principal que o visualizador de anexos fornece:

+ Veja todos os tipos de anexos suportados pelo Gerenciamento de documentos (arquivos, imagens, URLs e notas).
+ Exiba arquivos TIFF de várias páginas.
+ Execute as seguintes ações em arquivos de imagem:
  + Realce as partes da imagem.
  + Bloqueie as partes da imagem.
  + Adicione notas à imagem.
  + Aumente ou diminua o zoom na imagem.
  + Filtre a imagem.
  + Desfaça e refaça ações.
  + Ajuste o tamanho da imagem.

> [!NOTE]
> Essas ações estão disponíveis apenas para arquivos de imagem (JPEG, TIFF, PNG, etc.). Todas as alterações que você faz em uma imagem usando essas ações são salvas no arquivo de imagem. Atualmente, o visualizador de anexos não inclui capacidades de controle de versão ou auditoria.

### <a name="default-attachment"></a>Anexo padrão

Se uma fatura de fornecedor tiver mais de um anexo, você pode definir um dos documentos como anexo padrão na página **Anexos**. A opção **Anexo é o padrão** é uma nova opção que é adicionada como parte desse recurso. Esta opção também está exposta na entidade de dados de anexo do documento de fatura de fornecedor. Portanto, o anexo padrão pode ser configurado através de integrações.

Apenas um documento pode ser configurado como anexo padrão. Depois de configurar um documento como anexo padrão, ele é exibido automaticamente no visualizador de anexos quando a fatura é aberta. Se você não definir nenhum documento como anexo padrão, o visualizador não mostrará automaticamente nenhum anexo quando a fatura for aberta.

### <a name="showhide-invoice-attachments"></a>Mostrar/ocultar anexos de fatura

Um novo botão que está disponível nas páginas de consulta **Processamento de exceções**, **Fatura em aberto**, e **Diário de fatura** permite exibir ou ocultar o visualizador de anexo.

### <a name="security"></a>Segurança

As seguintes ações no visualizador de anexos são controladas por meio de segurança baseada em função:

+ Realce
+ Bloquear
+ Nota

### <a name="pending-vendor-invoices-page"></a>Página de faturas de fornecedor em aberto

Os seguintes privilégios fornecem acesso somente leitura ou acesso de leitura/gravação ao visualizador de anexos para as ações de destaque, bloqueio e anotação:

+ **Manter a imagem de fatura de fornecedor** – Esse privilégio fornece acesso de leitura/gravação.
+ **Exibir a imagem de fatura de fornecedor** – Esse privilégio fornece acesso somente leitura.

Os seguintes deveres fornecem acesso somente leitura ou acesso de leitura/gravação ao visualizador de anexos para essas ações:

+ **Manter faturas de fornecedor** – O privilégio Manter imagem da fatura do fornecedor é atribuído a este dever.
+ **Consultar status da fatura de fornecedor** – O privilégio de Exibir imagem da fatura de vendedor é atribuído a este dever.

As seguintes funções fornecem acesso somente leitura ou acesso de leitura/gravação ao visualizador de anexos para essas ações:

+ **Funcionário de contas a pagar** e **Gerente de contas a pagar** – O dever Manter faturas de fornecedor é atribuído a essas funções.
+ **Funcionário de contas a pagar**, **Gerente de contas a pagar**, **Funcionário de pagamento centralizado de contas a pagar** e **Funcionário de pagamentos de contas a pagar** – O dever Consultar status da fatura de fornecedor é atribuído a essas funções.

### <a name="invoice-exception-details-page"></a>Página de detalhes de exceção de fatura

Os seguintes privilégios fornecem acesso somente leitura ou acesso de leitura/gravação ao visualizador de anexos para as ações de destaque, bloqueio e anotação.

> [!NOTE]
> Fora da caixa, as funções mencionadas nesta seção fornecem acesso somente leitura às imagens de fatura no visualizador de anexos. Se uma função também precisar ter acesso de gravação às imagens, você pode conceder acesso de gravação a essa função usando o privilégio e o dever que são descritos aqui.

+ **Manter imagem da entidade de cabeçalho da fatura de fornecedor** – Este privilégio fornece acesso de leitura/gravação às imagens da fatura no visualizador de anexos.
+ **Exibir imagem de entidade de cabeçalho da fatura de fornecedor** – Este privilégio fornece visualização somente leitura para a imagem da fatura no visualizador de anexos.

Os seguintes deveres fornecem acesso somente leitura ao visualizador de anexos para essas ações:

+ **Manter faturas de fornecedor** – O privilégio Manter imagem da entidade de cabeçalho da fatura de fornecedor é atribuído a este dever.

As seguintes funções fornecem acesso somente leitura ao visualizador de anexos para essas ações:

+ **Funcionário de contas a pagar** e **Gerente de contas a pagar** – O dever Manter faturas de fornecedor é atribuído a essas funções.

Por padrão, se a função do usuário fornecer direitos de edição em qualquer página, o usuário também terá direitos de edição no visualizador de anexos para as ações de destaque, bloqueio e anotação. No entanto, se houver cenários em que uma função específica deve ter direitos de edição na página, mas não no visualizador de anexos, os privilégios apropriados da lista anterior podem ser usados para satisfazer o caso de uso.
