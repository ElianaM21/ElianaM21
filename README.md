- 👋 Hi, I’m @ElianaM21
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...


class Nodo:
    def __init__(self, valor):
        self.valor = valor
        self.izquierda = None
        self.derecha = None

class ArbolBinario:
    def __init__(self):
        self.raiz = None

    def insertar(self, valor):
        self.raiz = self._insertar(self.raiz, valor)

    def _insertar(self, nodo, valor):
        if nodo is None:
            return Nodo(valor)
        if valor < nodo.valor:
            nodo.izquierda = self._insertar(nodo.izquierda, valor)
        elif valor > nodo.valor:
            nodo.derecha = self._insertar(nodo.derecha, valor)
        return nodo

    def peso(self):
        return self._peso(self.raiz)

    def _peso(self, nodo):
        if nodo is None:
            return 0
        return 1 + self._peso(nodo.izquierda) + self._peso(nodo.derecha)

    def orden(self):
        resultado = []
        self._orden(self.raiz, resultado)
        return resultado

    def _orden(self, nodo, resultado):
        if nodo:
            self._orden(nodo.izquierda, resultado)
            resultado.append(nodo.valor)
            self._orden(nodo.derecha, resultado)

    def altura(self):
        return self._altura(self.raiz)

    def _altura(self, nodo):
        if nodo is None:
            return 0
        izquierda = self._altura(nodo.izquierda)
        derecha = self._altura(nodo.derecha)
        return 1 + max(izquierda, derecha)

# Ejemplo de uso
arbol = ArbolBinario()
valores = [10, 5, 15, 3, 7, 12, 18]

for valor in valores:
    arbol.insertar(valor)

print("Peso del árbol:", arbol.peso())
print("Orden del árbol:", arbol.orden())
print("Altura del árbol:", arbol.altura())


<!---
ElianaM21/ElianaM21 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
