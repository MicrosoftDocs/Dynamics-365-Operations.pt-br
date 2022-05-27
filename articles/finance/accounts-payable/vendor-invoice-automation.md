---
title: Automação de fatura para documentos digitalizados
description: Este tópico explica os recursos disponíveis para a automação ponta a ponta de notas fiscais de fornecedor, até mesmo notas fiscais que incluem anexos.
author: abruer
ms.date: 03/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 02fcb6ce49156c32f23bfb37478a1076f62aa868
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716384"
---
# <a name="invoice-automation-for-scanned-documents"></a>Automação de fatura para documentos digitalizados

[!include [banner](../includes/banner.md)]

Este tópico explica as entidades de dados disponíveis para a automação completa de faturas de fornecedor, incluindo faturas com anexos.

As organizações que desejam agilizar seus processos de Contas a Pagar (AP) geralmente identificam o processamento da fatura como uma das principais áreas de processo que devem ser mais eficientes. Em muitos casos, essas organizações descarregam o processamento de faturas em papel para um provedor de serviços de reconhecimento óptico de caracteres (OCR) de terceiros. Eles então recebem metadados de fatura legíveis por máquina, juntamente com uma imagem digitalizada de cada fatura. Para ajudar com a automação, uma solução de "última milha" foi construída para permitir o consumo desses artefatos no sistema de faturamento. Agora, esta automação de "última milha" é habilitada e pronta para uso, por meio de uma solução de automação de fatura.

## <a name="solution-context"></a>Contexto da solução

A solução de automação de fatura permite uma interface padrão que pode aceitar metadados de fatura para o cabeçalho da fatura e linhas de fatura, e também os anexos aplicáveis ​​à fatura. Qualquer sistema externo que possa gerar artefatos compatíveis esta interface poderá enviar o feed para o processamento automático de faturas e anexos.

A ilustração a seguir mostra um exemplo de cenário de integração onde a Contoso se associou com um provedor de serviços de OCR para processamento de fatura de fornecedor. Os fornecedores da Contoso enviam faturas ao provedor de serviços por e-mail. Através do processamento de OCR, o provedor de serviços gera metadados de fatura (cabeçalho e/ou linhas) e uma imagem digitalizada da fatura. Uma camada de integração transforma esses artefatos para que possam ser consumidos.

![Cenário de integração de amostra.](media/vendor_invoice_automation_01.png)

Várias variações do cenário anterior são possíveis se a integração da fatura for necessária. A migração de dados é outro caso de uso em que esta interface pode ser usada para criar faturas e anexos.

### <a name="solution-components"></a>Componentes da solução

A pegada de solução consiste nos seguintes componentes:

+ Entidades de dados para o cabeçalho da fatura, linhas de fatura e anexos de fatura
+ Processamento de exceção para faturas
+ Um visualizador de anexo lado a lado nas faturas

O restante deste tópico fornece descrições detalhadas desses componentes da solução.

## <a name="data-entities"></a>Entidades de dados

Um pacote de dados é a unidade de trabalho que deve ser enviada para que cabeçalhos de fatura, linhas de fatura e anexos de fatura possam ser criados. As seguintes entidades de dados são usadas para os artefatos que compõem o pacote de dados:

+ Cabeçalho da fatura de fornecedor
+ Linha de fatura de fornecedor
+ Anexo de documento de fatura de fornecedor

O anexo do documento de fatura do fornecedor é uma nova entidade de dados que é introduzida como parte desse recurso. A entidade do cabeçalho da fatura de fornecedor foi modificada para que ele suporte anexos. A entidade da linha de fatura do fornecedor não foi modificada para esse recurso.

Para obter informações detalhadas sobre pacotes de dados, consulte [Visão geral de gerenciamento de dados](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md). Para obter informações sobre como criar pacotes de dados usando o espaço de trabalho de gerenciamento de dados, consulte [Processar e consumir pacotes de dados na solução de aplicativos de finanças e operações do Dynamics 365](../../fin-ops-core/dev-itpro/lcs-solutions/process-data-packages-lcs-solutions.md).

Para gerar rapidamente dados de teste que incluem faturas e anexos, siga estas etapas.

1. Entre na sua instância.
1. Acesse **Contas a pagar** > **Faturas** > **Faturas de fornecedor em aberto**.
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
+ Quando o pacote de dados que contém as faturas é enviado para o Finance, o solicitante (ou seja, o aplicativo de integração que funciona fora do Finance) pode mencionar explicitamente a ID da empresa na solicitação HTTP. Nesse caso, o contexto da empresa em que o trabalho de processamento é executado no Finance é substituído, e as faturas são importadas para a empresa que foi passada por meio da solicitação HTTP.

> [!NOTE]
> Esse comportamento é um comportamento padrão de gerenciamento de dados. É explicado aqui, no contexto das faturas, apenas por uma questão de exaustividade.

## <a name="exception-processing"></a>Processamento de exceções

Nos cenários em que as faturas dos fornecedores entram no Finance and Operations por meio da integração, deve haver uma maneira fácil para um membro da equipe de contas a pagar processar exceções ou faturas que falharam e criar faturas pendentes fora das faturas que falharam. Esse processamento de exceção para faturas de fornecedores agora é parte do Finance and Operations.

### <a name="vendor-invoices-that-failed-to-import-list-page"></a>Faturas de fornecedores que não importaram páginas de lista

A página da lista nova para exceções de fatura está disponível em **Contas a pagar** > **Faturas** > **Importar falhas** > **Faturas de fornecedor que falharam na importação**. Esta página mostra todos os registros de cabeçalho da fatura de fornecedor na tabela de teste da entidade de dados do cabeçalho da fatura de fornecedor. Observe que você pode exibir os mesmos registros do espaço de trabalho **Gerenciamento de dados**. Você também pode executar as mesmas ações que são fornecidas no recurso de tratamento de exceção do espaço de trabalho **Gerenciamento de dados**. O recurso de tratamento de exceção foi otimizado para um usuário funcional, o que o torna mais fácil de usar.

![Página da lista de exceções.](media/vendor_invoice_automation_02.png)

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

A página da lista suporta as seguintes ações:

+ **Editar** – Abra a gravação de exceção no modo de edição, para que você possa resolver os problemas.
+ **Opções** – Acessar opções padrão disponíveis em páginas de listagem. Você pode usar a opção **Adicionar ao espaço de trabalho** para inserir a página da lista de exceções em seu espaço de trabalho como uma lista ou bloco.

### <a name="vendor-invoices-that-failed-to-import-details-page"></a>Faturas de fornecedores que não importaram páginas de informações

Quando o modo de edição é iniciado, a página **Faturas de fornecedor que falharam ao importar informações** de faturas com problemas é aberta. Se houver problemas em uma fatura com anexo, o anexo não será exibido. O anexo deve ser reanexado à fatura.

A página **Faturas de fornecedor que falharam ao importar informações** permite que você crie uma fatura pendente. Depois de corrigir os problemas na fatura como parte do processamento de exceções, selecione o botão **Criar fatura pendente** para criar a fatura pendente. A fatura pendente será criada em segundo plano. 

### <a name="shared-service-vs-organization-based-exception-processing"></a>Serviço compartilhado versus processamento de exceções baseado em organização

A página da lista de exceções suporta as construções de segurança padrão que a área de trabalho **Gerenciamento de dados** suporta para processamento dos registros de preparo. O trabalho de importação de fatura pode ser protegido das seguintes maneiras:

+ Por função de usuário
+ Por usuário
+ Por entidade legal

![Trabalho de importação garantido por função de usuário e entidade legal.](media/vendor_invoice_automation_04.png)

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

## <a name="security"></a>Segurança

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

### <a name="vendor-invoice-attachment"></a>Anexo da fatura de fornecedor

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
