Um dos primeiros pontos a verificar quando se estudam algoritmos  é a sua correcção, isto é, garantir que no fim da execução de um dado algoritmo com um input válido, produz um output correto.
Para isso usa-se a lógica de Hoare. Esta lógica consiste em triplos cujos componentes são a pré-condição, o programa a executar e a pós-condição.
   
 	{P} C {Q} 

Em que P é a pré-condição, Q a pós condição e C o programa a executar.
   
Para cada instrução básica existe uma regra lógica que permite avaliar a correcção do programa.
   
	 {Q[x->e]} x=e {Q}

 Esta regra verifica a validade das instruções de atribuição, que nos diz que Q se mantém verdadeiro após a atribuição de x.
    
	{P}C1;C2{Q}   ->   {P}C1{R}  &&  {R}C2{Q}

Esta regra mostra-nos a correcção da composição de instruções, em que a composição é válida se existir uma condição intermédia , que é pós condição do primeiro sub-programa e pré-condição do segundo, e a correcção dos dois sub-programas deve verificar-se.

  	{P} if (b) Ct else Cf {Q} -> {P && b} Ct {Q} && {P && nao(b)} Cf {Q}   

Esta regra mostra-nos que para verificar a correcção de uma instrução if em que quer a condição b for verdadeira e for executado o programa Ct, ou b for falso e se executar Cf, a pós-condição Q é verificada.

    Para a verificação de ciclos temos dois tipos de correcção: parcial e total. A correcção parcial implica que se a pré-condição for verificada à entrada do ciclo, quando o ciclo terminar, a pós-condição é verificada.
 Não garante no entanto que o ciclo termina, que só é imposto pela correcção total. Vamos começar por verificar a correcção parcial.
    
    {P} while(b) C {Q} => ( P->I && {I && b} C {I} && ( (I && nao(b))-> Q))     

Esta regra pressupõe a existência de um invariante que é verdadeiro no inicio do ciclo (P->I), que se mantem verdadeiro em todas as iterações do ciclo ({I && b} C {I}) e no fim do ciclo implica a pós-condição ((I && nao(b))-> Q).
 Este invariante prova assim que com sendo a pré-condição verificada, quando o ciclo termina, a pós condição também é verificada.
    
Um exemplo para melhor clarificar o conceito:

    // P={x=x0; y=y0>=0}
    i=0;
    res=0;
    while(i<y){ // I= { i<=y && res=i*x}
 	    res=res+x;
 	    i=i+1;
    }
    //Q={res=x0*y0}

