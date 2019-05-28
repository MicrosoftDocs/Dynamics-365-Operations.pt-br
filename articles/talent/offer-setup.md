---
title: Configurar o gerenciamento de ofertas
description: Este tópico descreve como configurar as ofertas no Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7fa0e5d30c06db16e105631e492af022acfcfd66
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517325"
---
# <a name="set-up-offer-management"></a>Configurar o gerenciamento de ofertas 

[!include [banner](includes/banner.md)]

Quando o candidato for movido para o estágio de oferta no Dynamics 365 for Talent: Attract, você precisará garantir que as ofertas podem ser rapidamente criadas, aprovadas, conforme necessário e enviadas para o candidato. Como a maioria de ofertas é padrão, elas podem ser criadas desde modelos reutilizáveis. No Attract, todas as ofertas são agrupadas em um pacote de oferta, que é uma coleção de um ou mais documentos de oferta. 

Este tópico lista todas as etapas que um administrador do Attract deve seguir para configurar diferentes modelos de pacote de oferta como parte do recurso de gerenciamento de ofertas no Attract. Os usuários com funções não administrativas não terão acesso a esses recursos.

>[!NOTE]
> Os recursos de gerenciamento de ofertas estão disponíveis como parte do complemento Contratação Abrangente.

## <a name="offer-data"></a>Dados da oferta 

Os dados da oferta são a menor unidade no modelo do pacote de oferta. Uma oferta típica consiste no texto padrão e em um conjunto de valores. Os conjuntos de valores são as únicas partes que podem mudar entre as ofertas. Durante a criação da oferta, o aspecto mais importante em que o criador da oferta pode se concentrar é a lista de espaços reservados de dados da oferta presentes em um modleo de pacote de oferta. Para configurar dados da oferta, faça o seguinte.

1.  Vá para **Gerenciamento de ofertas**.

1.  Expanda a seção **Biblioteca** no painel de navegação esquerdo, então vá para **Dados da oferta**.

    >[!NOTE]
    > Na página **Dados da oferta**, há as seções **Detalhes do candidato** e **Detalhes do trabalho**. O Attract fornece alguns espaços reservados de dados da oferta prontos para uso.
    
    > Há seções na página para organizar diferentes espaços reservados de dados da oferta diferentes em grupos lógicos. Estas seções podem ajudar na manutenção de dados da oferta e na população de dados durante o processo de criação da oferta.

1.  Para criar uma nova seção de dados da oferta, clique em **Adicionar uma seção** e insira um nome exclusivo para a seção.

1.  Para adicionar espaços reservados de dados da oferta a qualquer seção, clique em **Adicionar dados da oferta** e insira um nome exclusivo para o espaço reservado.

1.  Para editar o nome de qualquer seção, passe o mouse sobre o nome da seção e atualize o nome.

1.  Para editar o nome de qualquer espaço reservado de dados da oferta, primeiro verifique se o espaço reservado já não faz parte de um modelo. Em seguida, passe o mouse sobre o nome do espaço reservado de dados da oferta e atualize o nome como necessário.

1. Para excluir um espaço reservado de dados da oferta existente, primeiro verifique se o espaço reservado não faz parte de qualquer outro modelo. Em seguida, passe o mouse sobre o espaço reservado e, quando o ícone de lixeira aparecer, clique na lixeira para excluir o espaço reservado de dados da oferta.
    >[!NOTE]
    > Você pode ver de quantos modelos um espaço reservado de dados da oferta faz parte pelo número indicador ao lado de cada dado da oferta. 

1. Para excluir uma seção, passe o mouse sobre o nome. Se nenhum dos espaços reservados de dados da oferta dentro da sessão aparecer em algum modelo, você poderá clicar no ícone de lixeira para excluí-lo. 
    >[!NOTE]
    > A exclusão da seção também excluirá todos os espaços reservados de dados da oferta que estejam na seção.

Depois que os espaços reservados de dados da oferta tiverem sido configurados, você poderá usá-los em qualquer modelo de documento. Os espaços reservados de dados da oferta não estão restritos a um modelo específico -- o mesmo conjunto pode ser usado entre todos os modelos.

## <a name="offer-data-rules"></a>Regras de dados da oferta

A maioria das organizações tem regras para a forma como as ofertas devem ser criadas. Por exemplo, uma organização pode optar por exigir que a oferta de salário anual máximo para uma combinação de local específico e nível de tempo de serviço tenha de ficar dentro de um determinado intervalo, ou que haja somente alguns valores específicos possíveis para o nível da oferta para a nova contratação. No momento, o Attract dá suporte a todas essas regras de dados usando um arquivo CSV.

Para preparar o arquivo CSV de regras de dados, faça o seguinte.

1.  Determine o espaço reservado de dados da oferta para o conjunto de regras. Por exemplo, **Salário Anual**.

1.  Identifique os valores de espaço reservado de dados da oferta dependentes. Por exemplo, **Local de Trabalho** e **Nível**.

1.  Especifique as colunas 1 e 2 como **Local de trabalho** e **Nível**.

1.  Para carregar um valor de intervalo, crie as colunas 3 e 4 **Salário Anual**. Para carregar um valor específico em vez de um intervalo, crie somente a coluna 3 **Salário Anual**

1.  Preencha o arquivo do Microsoft Excel com base nas funções necessárias.

1.  Verifique se cada linha é uma combinação exclusiva de todos os valores.

1.  Salve o arquivo como um formato CSV.

Para carregar o arquivo de regras de dados da oferta, faça o seguinte.

1.  Vá para **Gerenciamento de ofertas**.

1.  Expanda a seção **Biblioteca** no painel de navegação esquerdo, então vá para **Regras de dados da oferta**.

1.  Clique em **Novo conjunto de dados** para exibir a caixa de diálogo **Upload**.

1.  Especifique um nome exclusivo para o conjunto de regras e então carregue o arquivo CSV salvo.

1.  Clique em **Adicionar**.
    O conjunto de regras será processado em segundo plano e você será notificado no aplicativo e por email quando ele for concluído.

    Você será notificado se houver um erro ao processar o upload. Você poderá então baixar o log de erros, corrigir o arquivo e carregá-lo novamente.

1.  Use a opção do botão de reticências (**…**) se quiser baixar o conjunto de regras e atualizar o conjunto de valores. Depois de atualizar, será possível carregar o arquivo novamente.

1.  Você pode excluir um upload de conjunto de regras existente se o espaço reservado que está sendo definida não estiver sendo usado em outro modelo de documento.

>[!NOTE]
> - Cada espaço reservado pode ter apenas um conjunto exclusivo de colunas do qual depende. Por exemplo, se **Salário Anual** depender do **Local de Trabalho** e de **Nível**, você não poderá carregar outro conjunto de regras onde **Salário Anual** depende de um conjunto diferente de colunas.

> - Você pode baixar conjuntos de dados da oferta de exemplo na guia **Exemplos** na página **Regras de dados da oferta** .

> - Quando um criador de oferta substitui os valores recomendados pelas regras de dados da oferta, a oferta é sinalizada como não padrão e o fluxo de trabalho de aprovação de oferta será obrigatório.

## <a name="document-templates"></a>Modelos de documento

Um modelo de documento de oferta pode ajudar os administradores a criarem cartas de oferta. O modelo de documento de oferta é uma combinação do texto que fará parte da oferta bem como os espaços reservados de dados da oferta definidos. 

Para criar um modelo de documento da oferta, faça o seguinte.

1.  Vá para **Gerenciamento de ofertas**.

1.  Expanda a seção **Biblioteca** no painel de navegação esquerdo e vá para **Modelos**.

    A página **Modelos** exibirá uma lista de modelos de documento que já foram definidos.

1.  Para criar um novo modelo de documento, clique em **Novo Modelo**.

1.  Insira um novo exclusivo para o modelo e clique em **Criar**.

1.  Use o editor de rich text para inserir ou editar o conteúdo do documenta da oferta. Você pode inserir tabelas, imagens e hiperlinks usando as opções disponíveis na parte superior do editor de texto.

1.  Você pode inserir espaços reservados de dados da oferta no documento de modelo da oferta:

    - Arrastando e soltando do painel direito.

    - Criando a hashtag do espaço reservado dos dados da oferta diretamente na posição. Digite **\#** e então comece a digitar o nome do espaço reservado de dados da oferta. As opções aparecerão na lista suspensa. Clique ou pressione **Enter** para inserir o espaço reservado de dados da oferta.

    >[!NOTE]
    > - Para associar um espaço reservado ao modelo de documento de oferta sem expor o valor ao candidato, passe o mouse sobre o espaço reservado de dados da oferta e clique no ícone **Fixar**. Isso enviará por push o espaço reservado para a seção **Dados da oferta fixados** do modelo de documento da oferta. Para desafixar, siga as mesmas etapas, mas clique em **Desafixar** na lista dos espaços reservados de dados da oferta.

    > - Para exibir a lista dos espaços reservados de dados da oferta ativos, alterne para a guia **Ativo** no painel direito.

    > - Se você inserir um espaço reservado orientado por um conjunto de regras de dados da oferta, poderá consultar a dependência do espaço reservado de dados da oferta em outros valores.

    > - Como alternativa, você pode **Importar** o conteúdo de um arquivo .docx no computador local e editar quando necessário. Dessa forma, não será necessário digitar todo o conteúdo no editor.

1. Para visualizar o documento da oferta, use a opção **Visualizar** na parte superior da página.

1. Para controlar se um criador da oferta pode editar o conteúdo de documentos da oferta, use a opção **Gerenciar permissão** na parte superior da página. Se desejar que o criador do oferta só insira valores de espaço reservado e não edite o o texto, defina o valor da permissão como **Não**.

1. Clique em **Salvar** para salvar seu progresso. O modelo será salvo em um estado de rascunho.

1. Para finalizar e marcar o documento como publicado, clique em **Concluir**.

1. Você pode ver quais modelos de documento estão atualmente ativos, no modo de rascunho e que foram arquivados e não são mais usados na experiência de aterrissagem da biblioteca de modelos de documento.

>[!NOTE]
> Você pode excluir qualquer modelo de documento da oferta que não faça parte de um modelo de pacote da oferta existente.


## <a name="offer-package-templates"></a>Modelos de pacote da oferta

Os pacotes da oferta são os artefatos da oferta compartilhados com o candidato e consistem em uma combinação de um ou mais modelos de documenta da oferta. Para criar um pacote da oferta, faça o seguinte.

1.  Vá para **Gerenciamento de ofertas**.

1.  Vá para **Pacotes** do painel esquerdo de navegação.

    Uma lista de modelos de pacote ativos que estão disponíveis para uso dos criadores da oferta é exibida.

1.  Para criar um novo pacote da oferta, clique em **Novo Pacote**.

1.  Insira um novo exclusivo e clique em **Criar**.

1.  Clique em **Adicionar modelo**.

    >[!NOTE]
    > - Você pode optar por criar um novo modelo ou escolher um existente.

    > - Se você optar por adicionar um modelo existente, precisará garantir que o modelo de documenta da oferta foi salvo, finalizado e marcado como ativo.
    
    > - É possível escolher quantos modelos de documento você quiser. 
    
1.  Clique em **Concluído** para retornar para **Gerenciamento de pacotes**.

    Você pode configurar a sequência dos documentos e também marcar se o documento da oferta específica será necessário durante a criação da oferta. O criador da oferta terá uma opção de excluir os documentos marcados como **Não necessário**.

1. Para salvar o modelo de pacote da oferta para que ele seja útil para todos os criadores da oferta, clique em **Salvar e publicar**.

   Para exibir modelos de pacote da oferta de rascunho, vá para a guia **Rascunhos**. Se uma alteração for feita no modelo de pacote da oferta, ele deverá ser salvo e republicado.

## <a name="configure-an-offer-process"></a>Configurar um processo de oferta

Há várias partes do processo de criação da oferta que podem ser configuradas por um administrador do Attract.

- **Aprovações da oferta** - escolha se as aprovações da oferta serão necessárias antes que a oferta possa ser enviada para o candidato. Como administrador, você também pode decidir se todas as aprovações de oferta acontecerão de maneira sequencial ou em um fluxo de trabalho de aprovação paralelo. Você também pode autorizar se os aprovadores da oferta devem adicionar um comentário junto com a aprovação da oferta. As aprovações da oferta são obrigatórias para todas as ofertas não padronizadas.

- **Experiência de oferta do candidato** - como administrador, você pode optar por definir se todas as ofertas terão uma data de vencimento, e nesse caso, qual deverá ser a contrapartida padrão para a data de vencimento. Você também pode configurar se os candidatos poderão recusar uma oferta.

- **Assinaturas eletrônicas** - como administrador, você pode escolher o método que os candidatos possam usar para assinar ofertas.
    - Adobe Sign - todos os pacotes de ofertas serão enviados e assinados via Adobe Sign. Cada criador de oferta que publica as necessidades de oferta para ter a conta do Adobe Sign conectada ao Attract. Para obter licenças e uma versão de avaliação gratuita do Adobe Sign, visite este [link](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).

    - DocuSign - todos os pacotes de ofertas serão enviados e assinados via DocuSign. Cada criador de oferta que publica as necessidades de oferta para ter a conta do DocuSign conectada ao Attract. 
    
    - ESign - esta é a opção padrão, pronta para usar, em que o usuário pode assinar uma oferta digitando seu nome e iniciais.


Para saber mais sobre o processo de criação da oferta, consulte [Criação, aprovação, e ofertas de assinatura](./creating-offers.md).
