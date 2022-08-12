---
title: Executar scripts X + + personalizados com tempo de inatividade zero
description: Este artigo descreve como carregar e executar pacotes implantáveis que contêm scripts X + + personalizados sem precisar suspender o sistema.
author: AndersGirke
ms.date: 12/16/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-12-16
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: aad48fbd3ee2f28f39f6061b5e922f5c4f47c8f6
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103510"
---
# <a name="run-custom-x-scripts-with-zero-downtime"></a>Executar scripts X + + personalizados com tempo de inatividade zero

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Esse recurso permite carregar e executar pacotes implantáveis que contêm scripts X + + personalizados sem precisar passar pelos Microsoft Dynamics Lifecycle Services (LCS) ou suspender o sistema. Portanto, você pode corrigir inconsistências mínimas dos dados sem causar nenhum tempo de inatividade.

A vantagem de usar um script X + + para corrigir inconsistências de dados menores é que o sistema ajustará automaticamente todas as tabelas relacionadas, conforme necessário, ao executar o script. Essa abordagem ajuda a garantir a integridade da correção e ajuda a minimizar o risco de introduzir novas inconsistências.

> [!IMPORTANT]
> Este recurso destina-se apenas à correção de inconsistências de dados menores. Ele não deve ser usado para as seguintes finalidades ou para qualquer outra finalidade:
>
> - Coleta de dados
> - Alterações de esquema
> - Migração de dados ou outros processos de longa duração
> - Correção de dados que podem ser corrigidos por outros meios, como processos comerciais regulares, ferramentas de consistência de dados ou outras ferramentas de autoatendimento
>
> O recurso permite que os usuários autorizados alterem entidades e seus registros diretamente, sem ter que executar a lógica comercial associada a essas entidades. Essas alterações podem causar problemas de integridade de dados. Portanto, sua organização pode exigir que você obtenha aprovação e aprovação de auditores internos e externos (ou outros participantes equivalentes) antes e/ou depois de executar um script. Por motivos de conformidade, as alterações que afetam algumas características também devem ser divulgadas nos relatórios externos (como demonstrativos financeiros) ou relatadas a autoridades governamentais. Sua organização é o único responsável pelas alterações feitas em seus dados por meio deste recurso, qualquer aprovação e aprovação ou revelação dessas alterações, bem como a conformidade com as leis aplicáveis. Você assume todos os riscos de usar esse recurso.

Todos os pacotes implantáveis que são carregados no sistema passam por um fluxo de trabalho obrigatório. Como precaução de segurança, e para ajudar a garantir a diferenciação de direitos, o usuário que carrega um pacote implantado não tem permissão para aprová-lo para as próximas etapas do fluxo de trabalho. Outro usuário deverá aprová-lo. No entanto, depois que o pacote for aprovado, o usuário que o carregou terá permissão para concluir as etapas restantes.

O sistema requer que todos os pacotes implantáveis passem por uma execução de teste. Antes que o script possa ser executado em dados de produção, um usuário deve validar se a saída está correta selecionando **Aceitar log de teste**. Se a saída não estiver correta, o usuário deverá marcar o pacote como falha, selecionando **Abandonar**. Nesse caso, não será permitido que o script seja executado em dados de produção.

Todo pacote carregado é salvo no sistema e passa por um fluxo de trabalho de eventos definido. Para cada evento, o sistema mantém um log que inclui um carimbo de data/hora e a identidade da pessoa que executou o evento. Dessa forma, o sistema garante que haverá uma trilha de auditoria.

Como mostra a ilustração a seguir, o sistema fornece detalhes sobre como cada pacote implantado foi executado em X + + e quais entidades foram tocadas.

![Página de detalhes do script.](media/script-details.png "Página de detalhes do script")

## <a name="assign-duties-to-users-to-control-access"></a>Atribuir direitos a usuários para controlar o acesso

Esse recurso oferece os seguintes direitos. Os administradores podem usar esses direitos para ajudar a controlar o acesso ao recurso.

- **Manter scripts personalizados** – esse imposto concede a capacidade de carregar, testar, verificar e executar scripts personalizados X + + em ambientes (teste de aceitação do usuário \[UAT\] e produção).
- **Aprovar scripts personalizados** – este imposto concede a capacidade de aprovar um script X + + personalizado carregado. A aprovação é uma etapa obrigatória antes que qualquer script possa ser testado, verificado e executado.

Para ajudar a minimizar o risco de ação mal-intencionada, cada script deve ser explicitamente aprovado por um usuário diferente daquele que o carregou. Para que você possa usar esse recurso em sua organização, um administrador deve atribuir os direitos anteriores a pelo menos dois usuários relevantes e altamente confiáveis. Embora um único usuário possa ter os dois direitos, esse usuário ainda não poderá aprovar seus próprios scripts.

## <a name="create-a-deployable-package"></a>Criar um pacote implantável

O recurso requer um pacote implantado comum que pode ser criado no Visual Studio. Para obter instruções, consulte [Criar pacotes implantáveis de modelos](../deployment/create-apply-deployable-package.md).

Seu pacote implantável deve conter exatamente uma classe X + + executável. Em outras palavras, ele deve ter uma classe que inclua um método com a seguinte assinatura.

```xpp
public static void main(Args _args)
```

> [!NOTE]
> O nome do método principal deve estar em letras minúsculas.

## <a name="code-example"></a>Código de exemplo

O exemplo de código a seguir mostra como um pacote implantável pode ser estruturado.

```xpp
class MyScriptClassForIssueXYZ
{
    public static void main(Args _args)
    {
        if (curExt() != 'DAT')
        {
            throw error("This script must run in the DAT company!");
        }

        ttsbegin;

        MyTable myTable;

        update_recordset myTable
            setting myField = 17
            where myTable.myReference == 'xyz';

        if (myTable.RowCount() != 1)
        {
            throw error("Not updating the expected row!");
        }

        info("Success");
  
        ttscommit;
    }

}
```

## <a name="best-practices"></a>Práticas Recomendadas

A lista a seguir descreve algumas das práticas recomendadas para gravar, implementar e executar um script com êxito. A lista não é completa e deve ser considerada somente uma guia.

- **Grave** uma mensagem de êxito no final do script. Dessa forma, você poderá ver se o script foi executado sem exceções.
- **Adicione** manipulação explícita do escopo da transação.
- **Use** a lógica comercial existente, como métodos `update()`, mas **não** ignore a lógica comercial usando os métodos `doUpdate()`, `doInsert()` e `doDelete()`. Essa abordagem irá ajudar a garantir que os dados dependentes sejam tratados corretamente. Ele também reduzirá significativamente o risco de inconsistências de dados.
- **Declare** o contexto da empresa. Essa abordagem irá expor erros comuns quando um script for executado. Por exemplo, ele revelará se o script está sendo executado na empresa errada.
- **Declaram** que o número de registros afetados corresponde às suas expectativas. Esta abordagem revelará se os dados foram deslocados inesperadamente no sistema enquanto o script estava sendo preparado.
- **Use** nomes de classe exclusivos para cada script (por exemplo, incluindo uma referência a um item de trabalho no nome). Essa abordagem impedirá problemas de conflito de nomes quando você carregar o script. Se for necessária uma nova iteração de um script, certifique-se de dar a ele um novo nome.
- **Teste** cada script em um ambiente que não seja de produção primeiro. Teste o impacto pretendido e para efeitos colaterais não intencionais sobre dados relacionados. Certifique-se de que todos os processos comerciais que podem ser afetados possam ser bem e totalmente concluídos posteriormente.

## <a name="upload-and-run-a-deployable-package"></a>Carregue e execute um pacote implantado

Use os seguintes procedimentos para carregar e executar um script.

1. No seu aplicativo de finanças e operações, vá para **Administração do sistema \> Tarefas periódicas \> Banco de dados \> Scripts personalizados**.
1. Selecione **Carregar**.
1. Selecione o pacote implantável criado, conforme descrito anteriormente neste artigo. Será solicitado que você especifique a finalidade do script.
1. Agora, o script deve ser aprovado por um usuário diferente do usuário que o carregou. O aprovador deve seguir estas etapas:

    1. Vá para **Administração do sistema \> Periódico \> Banco de dados \> Scripts personalizados**.
    1. Selecione o script a ser aprovado e selecione **Detalhes**.
    1. No Painel de Ações, na guia **Fluxo de trabalho do processo**, no grupo **Iniciar**, selecione **Aprovar** ou **Rejeitar**. Se você selecionar **Aprovar**, o script será marcado como aprovado e será desbloqueado para teste. Se você selecionar **Rejeitar**, o script será bloqueado. Nos dois casos, o evento será registrado e uma cópia do script será mantida no sistema.

1. O script deve ser testado para garantir que ele faz o que pretende fazer. O testador pode ser o mesmo que o carregador ou o aprovador, ou pode ser um terceiro usuário que tem as permissões necessárias. O testador deve seguir estas etapas:

    1. Vá para **Administração do sistema \> Periódico \> Banco de dados \> Scripts personalizados**.
    1. Selecione o script a ser testado e selecione **Detalhes**.
    1. No Painel de Ações, na guia **Fluxo de trabalho do processo**, no grupo **Teste**, selecione **Executar teste**. O script é executado em uma transação temporária que o sistema irá abortar automaticamente enquanto coleta vários logs e instruções SQL.
    1. Quando o script tiver concluído a execução, revise os logs e verifique se os resultados atendem às suas expectativas. Siga uma destas etapas:

        - Se você estiver satisfeito com o resultado do teste, selecione **Aceitar log de teste** no grupo **Teste** na guia **Fluxo de trabalho do processo** do Painel de Ações, para permitir que o script seja executado. O log de eventos refletirá o fato de que o script foi testado e indicará quem o testou e quando.
        - Se você estiver satisfeito com o resultado do teste, selecione **Abandonar** no grupo **Finalizar** na guia **Fluxo de trabalho do processo** do Painel de Ações, para impedir a execução do script. O sistema manterá uma cópia do script juntamente com um log do histórico.

1. Quando tiver certeza de que o script atende às suas expectativas, selecione **Executar** no grupo **Executar** na guia **Fluxo de trabalho do processo** do Painel de Ações para executá-lo. Este comando faz a mesma coisa que o teste anterior executado, mas a transação será confirmada no final.
1. Depois que o script terminar de ser executado, verifique o resultado e confirme se o script funcionou conforme o esperado. Siga uma destas etapas:

    - Se você estiver satisfeito com o resultado, selecione **Finalidade resolvida** no grupo **Finalizar** na guia **Processo de fluxo de trabalho** do Painel de Ações. O log de eventos refletirá o fato de que o script foi executado com sucesso e isso indicará quem verificou o script e quando. O script foi salvo, mas agora está bloqueado e não pode ser executado novamente.
    - Se você estiver satisfeito com o resultado, selecione **Finalidade não resolvida** no grupo **Finalizar** na guia **Processo de fluxo de trabalho** do Painel de Ações. O log de eventos refletirá o fato de que o script não atendeu o objetivo pretendido e isso indicará quem executou o script e quando. O script foi salvo, mas agora está bloqueado e não pode ser executado novamente. No entanto, o sistema não desfaz automaticamente a ação do script. Talvez seja necessário escrever, importar e executar um novo script para desfazer o efeito que o script que falhou tem no seu sistema.

A seleção na última etapa define o estado final do script. Você pode repetir o processo, conforme necessário.

## <a name="upload-and-run-a-deployable-package-through-lcs"></a>Carregue e execute um pacote implantado pelo LCS

Em vez de implantar seu pacote implantado por meio da interface do usuário para seu aplicativo de finanças e operações, conforme descrito na seção anterior, você pode carregá-lo para LCS e usar o procedimento regular para implantá-lo. Para obter mais informações, consulte [Instalar pacotes implantáveis da linha de comando](../deployment/install-deployable-package.md).

Embora essa abordagem tenha menos restrições, ela fornece menos proteção de erro. Além disso, por exigir uma reinicialização de todos os servidores, isso causará algum tempo de inatividade.

