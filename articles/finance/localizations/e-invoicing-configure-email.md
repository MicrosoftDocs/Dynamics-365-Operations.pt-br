---
title: Configurar um canal de email
description: Este artigo explica como configurar um canal de email para receber faturas eletrônicas.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9227b032ffe896ad6a67962e5047fd797a883ae1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902375"
---
# <a name="configure-an-email-channel"></a>Configurar um canal de email

[!include [banner](../includes/banner.md)]

Se o recurso de Faturamento eletrônico criado importar faturas eletrônicas de fornecedor de arquivos anexos recebidos por email, recomendamos que você configure um canal de conta de email.

1. Selecione o recurso de faturamento eletrônico que você criou no Regulatory Configuration Service (RCS). Certifique-se de selecionar a versão com o status **Rascunho**.
2. Na guia **Configurações**, selecione **Adicionar**.
3. Na caixa de diálogo **Criar configuração do recurso** na caixa de diálogo suspensa, no grupo de campos **Novo**, selecione a opção **Configuração personalizada**:
4. No grupo de campos **Tipo de configuração**, selecione a opção **Canal de dados**.
5. No campo **Selecionar canal de dados**, digite o **Email de entrada**.
6. Selecione **Criar**.
7. Selecione a linha que você criou antes e selecione **Editar**.
8. Na guia **Canal de dados**, na seção **Parâmetros**, defina os seguintes campos obrigatórios.

    | Campo                | Descrição |
    |----------------------|-------------|
    | Canal de dados         | Digite um nome exclusivo para identificar o canal de dados. O nome pode ter no máximo 10 caracteres. Ele será referenciado nas regras de aplicabilidade e em aplicativos conectados durante o processo de comunicação. |
    | Endereço do servidor       | Digite o endereço de servidor do provedor da conta de email. Por exemplo, o endereço do servidor para o provedor `https://outlook.live.com` é imap-mail.outlook.com. |
    | Porta do servidor          | Insira o número da porta usada pelo provedor da conta de email. Por exemplo, a porta do servidor para o provedor `https://outlook.live.com` é 993. |
    | Segredo do nome do usuário     | Digite o nome do segredo do Microsoft Azure Key Vault que contém a ID da conta de usuário de email. Esse segredo deve ser criado no Key Vault e configurado no seu ambiente de serviço. |
    | Segredo da senha do usuário | Digite o nome do segredo do Key Vault que contém a senha da conta de usuário de email. |
    | Tempo limite              | O limite de tempo máximo, em milissegundos (MS), que o sistema deve esperar por uma resposta. O valor padrão é 10.000 ms (10 segundos). |
    | Pasta principal          | Especifique a fonte de importação de email ou a pasta da qual o serviço deve processar emails. |
    | Pasta de arquivo morto       | Especifique a pasta na qual os emails processados devem ser armazenados. Se você não especificar essa pasta, o sistema a criará automaticamente. |
    | Pasta de erros         | Especifique a pasta para a qual o sistema deve mover os emails para se o processamento falhar. Se você não especificar essa pasta, o sistema a criará automaticamente. |
    | Tamanho máximo da mensagem     | Insira o tamanho máximo, em bytes, de uma única mensagem processada. O valor padrão é 20.000.000 bytes. |
    | Número máximo de mensagens   | Digite a quantidade máxima de mensagens a serem processadas para uma única ação. Se não desejar limitar o número de mensagens, defina o valor como **0** (zero). |
    | Filtro de remetente          | Insira uma cadeia de caracteres para filtrar por endereço do remetente. Somente os emails nos quais o endereço do remetente corresponde ao filtro serão processados. Esse campo é opcional. Para especificar vários endereços de remetentes, use ponto-e-vírgula (;) como separadores. |
    | Filtro de assunto       | Insira uma cadeia de caracteres para filtrar por assunto. Somente os emails nos quais o assunto corresponda ao filtro serão processados. Esse campo é opcional. Há suporte para uma máscara simples, tal como **\*smth\*.ext**, na qual cada asterisco (\*) representa zero ou mais ocorrências de qualquer caractere. |
    | Filtro de data          | Especifique uma data para definir a idade máxima, em dias, das mensagens que são processadas. Esse campo é opcional. O valor padrão é 30 dias. |
    | Modo de processamento      | <p>Selecione uma das opções a seguir para especificar se todos os anexos em um email podem ser processados juntos ou se cada anexo deve ser processado separadamente:</p><ul><li><b>Por anexo</b> – Um novo documento eletrônico será criado para cada anexo do email. Por exemplo, se um email incluir vários arquivos que contenham dados de fatura eletrônica, cada arquivo será considerado uma nova fatura eletrônica no sistema.</li><li><b>Por email</b> – Um anexo será considerado um anexo base e uma fatura eletrônica será criada no sistema. Outros anexos podem ser usados como arquivos de suporte.</li></ul> |

9. Na seção **Filtro de anexos**, adicione as informações de filtragem de arquivos. Somente anexos que satisfaçam ao filtro definido serão processados. Por exemplo, **\*.xml** filtrará os anexos que têm a extensão de nome de arquivo .xml. O nome do anexo é usado no Dynamics 365 Finance ou no Dynamics 365 Supply Chain Management durante a instalação.

    - Se você definir o campo **Modo de processamento** como **Por email** na etapa anterior, poderá adicionar vários filtros aqui. O nome identificará o documento específico.
    - Se você definir o campo **Modo de processamento** como **Por anexo**, só poderá adicionar um filtro.

10. Na guia **Regras de aplicabilidade**, revise e atualize os critérios, conforme necessário. O valor do campo **Canal** deve ser igual ao valor inserido no campo **Canal de dados** na etapa 8.
11. Selecione **Salvar** e feche a página.
