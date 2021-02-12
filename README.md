# arvore-aula3

// valores da arvore

package árvore;

public class arvoremain {

	public static void main(String[] args) {
		
		Arvore<Integer> arvore = new Arvore <Integer>();
		arvore.adicionar(10);
		arvore.adicionar(8);
		arvore.adicionar(5);
		arvore.adicionar(9);
		arvore.adicionar(7);
		arvore.adicionar(18);
		arvore.adicionar(13);
		arvore.adicionar(20);
		Systen.out.println("Em-Ordem");
		arvore.emOrdem(arvore.getRaiz());

		Systen.out.println("\n\nPré-Ordem");
		arvore.preOrdem(arvore.getRaiz());

		Systen.out.println("\n\nPós-Ordem");
		arvore.posOrdem(arvore.getRaiz());

	}

}

// percorrendo a arvore

package árvore;

public class Arvore <TIPO extends Compareble> {
	

	public static void main(String args[]) {
		
		private Elemento<TIPO> raiz;
		
		public Arvore(){
			this.raiz = null;
			
		}
		
	    public void adicionar (TIPO valor) {
	    	Elemento<TIPO> novoElemento = new Elemento<TIPO>(valor);
	    	if (raiz == null){
			this.raiz = novoElemento;
	    	}else{
	    		Elemento<TIPO> atual = this.raiz;
	    		
	    	while (true) {
	    		if (novoElemento.getValor() .comparebleTo (atual.getValor()) == -1) {
	    			if (atual.getEsquerda() != null) {
	    				atual = atual.getEsquerda();
	    				
	    			}else{
	    				atual.setEsquerda(novoElemento);
	    				break;
	    			}
	    			
	    		}else{
	    			if (atual.getDireita() != null) {
	    				atual = atual.getDireita();
	    				
	    			}else{
	    				atual.setDireita(novoElemento);
	    				break;
	    			
	    				}
	    			}
	    		}
		}
	
	}

	public Elemento<TIPO> getRaiz() {
		return raiz;
	}

// imprimindo em ordem

	public static void emOrdem(Elemento<TIPO> atual) {
		if (atual != null) {
			emOrdem(atual.getEsquerda());
			System.out.println(atual.getValor());
			emOrdem(atual.getDireita());
		}
	}

// imprimindo pré ordem

	public static void preOrdem(Elemento<TIPO> atual) {
		if (atual != null) {
			System.out.println(atual.getValor());
			preOrdem(atual.getEsquerda());
			preOrdem(atual.getDireita());
			
		}
	}

// imprimindo pós ordem

	public static void posOrdem(Elemento<TIPO> atual) {
		if (atual != null) {
			posOrdem(atual.getEsquerda());
			posOrdem(atual.getDireita());
			System.out.println(atual.getValor());
		}
	}


}

}
