Descrição da Atividade

O funcionamento de threads em Java, destaca diferentes níveis de prioridade e impactam a execução de tarefas. 
A execução de Alta Prioridade é configurada com prioridade máxima e executa loops curtos com pausas (sleep(10)).
Já a execução de Baixa Prioridade é configurada com prioridade mínima e executa loops infinitos imprimindo mensagens continuamente.

Tendo como objetivo demonstrar a influência de prioridades no agendamento de threads pelo sistema operacional.
Utilizando recursos como shutdown hooks para interromper as threads de maneira controlada.

Explicação do Código

Definição das Threads:
   BaixaPrioridade imprime continuamente "Thread de baixa prioridade executando -> 1".
   AltaPrioridade imprime "Thread de alta prioridade executando -> 10" cinco vezes seguidas, faz uma pausa de 10ms, e repete.

Classe LancadorPrioridade:
   Instancia as threads de alta e baixa prioridade.
   Inicia as threads com start().
   Usa yield() para ceder a execução temporariamente a outras threads.
   Implementa um Shutdown Hook para encerrar as threads quando o programa for finalizado.

Interrupção Controlada:
   As threads são interrompidas utilizando o método interrupt() ao final do programa e no Shutdown Hook.

Observações Importantes:
   Mesmo com prioridades configuradas, o comportamento pode variar dependendo do sistema operacional e da máquina virtual Java (JVM).
   A thread de alta prioridade não monopoliza a execução devido ao uso de pausas (sleep()), permitindo que a thread de baixa prioridade seja agendada ocasionalmente.

Análise do Comportamento

   Em sistemas preemptivos, a thread de alta prioridade geralmente domina a execução.
   A saída do terminal demonstra a alternância de mensagens entre as threads.
   Impacto do Shutdown Hook: Permite encerrar as threads de forma segura, prevenindo loops infinitos após a finalização do programa.
