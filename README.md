# Programa-oFuncional-
Encontrar uma média com o método reduce em JavaScript​
Em vez de registrar a soma, é possível dividir a soma pelo comprimento do array antes de retornar um valor final.
A maneira de fazer isso é tirar vantagem dos outros parâmetros do método reduce. O primeiro desses argumentos é o índice. Assim como em um laço for, o índice se refere ao número de vezes que o redutor fez o laço percorrendo o array. O último argumento é o próprio array.

const dolar = [29.76, 41.85, 46.5];

const media = dolar.reduce((total, valor, índice, array) => {
  total += valor;
  if( índice === array.length-1) { 
    return total/array.length;
  } else { 
    return total;
  }
});

media // 39.37

map e filter como reduções
duplicar o total, ou dividir cada número por dois antes de somá-los ou usar uma instrução if dentro do redutor para somar apenas os números que forem maiores que 10. O que quero dizer é que o método reduce em JavaScript
-retornar um único valor e reduzir um array a um outro array novo.
O valor inicial é o valor do parâmetro total quando a redução iniciar. Define o valor inicial adicionando uma vírgula, seguida por seu valor inicial dentro do parênteses, mas após as chaves.

const media = dolar.reduce((total, valor, índice, array) => {
  total += valor
  return total/array.length
}, 0);

Ao definir o valor inicial como sendo um array vazio, podemos fazer o push de cada valor para dentro de total. Se quiser reduzir um array de valores a um outro array onde cada valor é duplicado, fazendo o push de valor * 2. Depois, retor o total quando não houver mais valores a serem enviados ao novo array por push.

const valores = [29.76, 41.85, 46.5];
const duplicados = valores.reduce((total, valor) => {
  total.push(valor * 2);
  return total;
}, []);

duplicados // [59.52, 83.7, 93]
cada valor é duplicado. Também podem filtrar, excluindo números que não quer duplicar, adicionando uma instrução if ao nosso redutor.
const valores = [29.76, 41.85, 46.5];

const acimaDos30 = valores.reduce((total, valor) => {
  if (valor > 30) {
    total.push(valor);
  }
  return total;
}, []);

acimaDos30 // [ 41.85, 46.5 ]
Essas são as operações dos métodos map e filter reescritas como um método reduce.
Para esses exemplos, faria mais sentido usar map ou filter, pois eles são mais simples de usar. O benefício de se usar reduce está nos casos onde você quer usar map e filter juntos e tem muitos dados para examinar.
Se você encadear map e filter juntos, estará fazendo o trabalho duas vezes. Você filtra cada valor único e então mapeia os valores restantes. Com reduce, você pode filtrar e mapear em uma única passagem.
Usando map e filter, mas, quando começar a encadear diversos métodos juntos, é mais rápido usar reduce nos dados em vez disso.
