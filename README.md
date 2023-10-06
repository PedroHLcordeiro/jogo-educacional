# jogo-educacional
import random

# Dicionário de perguntas por matéria e nível
perguntas = {
    "Português": {
        0: [
            {"pergunta": "Qual é o verbo na frase 'O gato pula no telhado'?", "resposta": "pula"},
            {"pergunta": "O que é um substantivo?", "resposta": "uma palavra que nomeia algo"},
            {"pergunta": "Qual é o antônimo de 'feliz'?", "resposta": "triste"},
            {"pergunta": "Qual é o plural de 'menino'?", "resposta": "meninos"},
            {"pergunta": "Quantas sílabas tem a palavra 'cachorro'?", "resposta": "3"},
            {"pergunta": "O que é um adjetivo?", "resposta": "uma palavra que descreve um substantivo"},
            {"pergunta": "Quem é o autor da obra 'Dom Casmurro'?", "resposta": "Machado de Assis"},
            {"pergunta": "O que é um pronome pessoal?", "resposta": "uma palavra que substitui um nome"},
            {"pergunta": "Quantas consoantes tem a palavra 'escola'?", "resposta": "3"},
            {"pergunta": "Qual é o plural de 'gato'?", "resposta": "gatos"},
        ],
        1: [
            {"pergunta": "O que é uma metáfora?",
             "resposta": "uma comparação entre duas coisas sem usar 'como' ou 'como se'"},
            {"pergunta": "Qual é a função do ponto e vírgula em uma frase?", "resposta": "separar itens em uma lista"},
            {"pergunta": "O que é um ditongo?", "resposta": "uma sequência de duas vogais na mesma sílaba"},
            {"pergunta": "Qual é o plural de 'cachorro'?", "resposta": "cachorros"},
            {"pergunta": "O que é uma oração subordinada?",
             "resposta": "uma oração que não pode funcionar sozinha como uma frase completa"},
            {"pergunta": "Quem escreveu 'Memórias Póstumas de Brás Cubas'?", "resposta": "Machado de Assis"},
            {"pergunta": "O que é uma antítese?", "resposta": "a apresentação de ideias opostas em uma frase"},
            {"pergunta": "Qual é o feminino de 'cavalo'?", "resposta": "égua"},
            {"pergunta": "O que é uma elipse?", "resposta": "a omissão de palavras em uma frase"},
            {"pergunta": "Quem é a autora de 'A Casa dos Espíritos'?", "resposta": "Isabel Allende"},
        ],
        2: [
            {"pergunta": "Qual é o antônimo de 'verdadeiro'?", "resposta": "falso"},
            {"pergunta": "O que é uma aliteração?",
             "resposta": "a repetição de sons consonantais em uma sequência de palavras"},
            {"pergunta": "O que é uma anáfora?",
             "resposta": "a repetição de uma palavra ou frase no início de várias frases ou versos"},
            {"pergunta": "Qual é o superlativo de 'pequeno'?", "resposta": "o menor"},
            {"pergunta": "O que é uma sinestesia?",
             "resposta": "a mistura de diferentes sentidos em uma única expressão"},
            {"pergunta": "Qual é o antônimo de 'frio'?", "resposta": "quente"},
            {"pergunta": "O que é uma onomatopeia?", "resposta": "uma palavra que imita o som que representa"},
            {"pergunta": "Qual é o superlativo de 'longe'?", "resposta": "o mais distante"},
            {"pergunta": "Qual é o plural de 'mão'?", "resposta": "mãos"},
            {"pergunta": "Qual é o antônimo de 'bom'?", "resposta": "mau"},
        ],
        3: [
            {"pergunta": "O que é uma elocução?", "resposta": "o modo de se expressar"},
            {"pergunta": "Qual é a origem da palavra 'etimologia'?", "resposta": "grego"},
            {"pergunta": "O que é uma elipse?", "resposta": "a omissão de palavras em uma frase"},
            {"pergunta": "Quem é a autora de 'O Amor nos Tempos do Cólera'?", "resposta": "Gabriel García Márquez"},
            {"pergunta": "O que é uma antonomásia?", "resposta": "uso de um nome próprio como um nome comum"},
            {"pergunta": "Qual é o plural de 'país'?", "resposta": "países"},
            {"pergunta": "O que é uma silepse?", "resposta": "a concordância ideológica de gênero e número"},
            {"pergunta": "Qual é o antônimo de 'belo'?", "resposta": "feio"},
            {"pergunta": "Qual é o plural de 'cruz'?", "resposta": "cruzes"},
            {"pergunta": "O que é uma enumeração?", "resposta": "a apresentação de uma lista de itens"},
        ],
    },
    "Matemática": {
        0: [
            {"pergunta": "Quanto é 2 + 2?", "resposta": "4"},
            {"pergunta": "Qual é a raiz quadrada de 9?", "resposta": "3"},
            {"pergunta": "Quanto é 5 x 5?", "resposta": "25"},
            {"pergunta": "Quanto é 10 - 3?", "resposta": "7"},
            {"pergunta": "Qual é o resultado de 4 ÷ 2?", "resposta": "2"},
            {"pergunta": "Quanto é 3 x 7?", "resposta": "21"},
            {"pergunta": "Quanto é 8 + 4?", "resposta": "12"},
            {"pergunta": "Qual é a raiz quadrada de 16?", "resposta": "4"},
            {"pergunta": "Quanto é 9 - 6?", "resposta": "3"},
            {"pergunta": "Quanto é 20 ÷ 4?", "resposta": "5"},
        ],
        1: [
            {"pergunta": "Quanto é 12 x 8?", "resposta": "96"},
            {"pergunta": "Qual é a raiz quadrada de 25?", "resposta": "5"},
            {"pergunta": "Quanto é 18 ÷ 2?", "resposta": "9"},
            {"pergunta": "Quanto é 15 - 7?", "resposta": "8"},
            {"pergunta": "Quanto é 7 x 9?", "resposta": "63"},
            {"pergunta": "Quanto é 16 + 7?", "resposta": "23"},
            {"pergunta": "Qual é a raiz quadrada de 49?", "resposta": "7"},
            {"pergunta": "Quanto é 21 ÷ 3?", "resposta": "7"},
            {"pergunta": "Quanto é 14 - 6?", "resposta": "8"},
            {"pergunta": "Quanto é 25 ÷ 5?", "resposta": "5"},
        ],
        2: [
            {"pergunta": "Quanto é 30 x 4?", "resposta": "120"},
            {"pergunta": "Qual é a raiz quadrada de 64?", "resposta": "8"},
            {"pergunta": "Quanto é 36 ÷ 6?", "resposta": "6"},
            {"pergunta": "Quanto é 42 - 19?", "resposta": "23"},
            {"pergunta": "Quanto é 9 x 8?", "resposta": "72"},
            {"pergunta": "Quanto é 28 + 13?", "resposta": "41"},
            {"pergunta": "Qual é a raiz quadrada de 81?", "resposta": "9"},
            {"pergunta": "Quanto é 56 ÷ 7?", "resposta": "8"},
            {"pergunta": "Quanto é 17 - 9?", "resposta": "8"},
            {"pergunta": "Quanto é 64 ÷ 8?", "resposta": "8"},
        ],
        3: [
            {"pergunta": "Quanto é 72 x 6?", "resposta": "432"},
            {"pergunta": "Qual é a raiz quadrada de 100?", "resposta": "10"},
            {"pergunta": "Quanto é 90 ÷ 9?", "resposta": "10"},
            {"pergunta": "Quanto é 120 - 37?", "resposta": "83"},
            {"pergunta": "Quanto é 11 x 12?", "resposta": "132"},
            {"pergunta": "Quanto é 74 + 28?", "resposta": "102"},
            {"pergunta": "Qual é a raiz quadrada de 144?", "resposta": "12"},
            {"pergunta": "Quanto é 63 ÷ 9?", "resposta": "7"},
            {"pergunta": "Quanto é 32 - 19?", "resposta": "13"},
            {"pergunta": "Quanto é 144 ÷ 12?", "resposta": "12"},
        ],
    },
}


def jogar_quiz():
    print("Olá, Escolha uma matéria e nível para começar o quiz.")

    # Listar matérias disponíveis
    materias_disponiveis = list(perguntas.keys())
    for i, materia in enumerate(materias_disponiveis):
        print(f"{i + 1}. {materia}")

    # Solicitar a escolha da matéria
    escolha_materia = int(input("Escolha o número da matéria: ")) - 1

    # Verificar se a escolha é válida
    if 0 <= escolha_materia < len(materias_disponiveis):
        materia_selecionada = materias_disponiveis[escolha_materia]
        niveis_disponiveis = list(perguntas[materia_selecionada].keys())

        # Listar níveis disponíveis
        print(f"\nNíveis disponíveis para {materia_selecionada}:")
        for i, nivel in enumerate(niveis_disponiveis):
            print(f"{i + 1}. Nível {nivel}")

        # Solicitar a escolha do nível
        escolha_nivel = int(input("Escolha o número do nível: ")) - 1

        # Verificar se a escolha do nível é válida
        if 0 <= escolha_nivel < len(niveis_disponiveis):
            nivel_selecionado = niveis_disponiveis[escolha_nivel]
            perguntas_nivel = perguntas[materia_selecionada][nivel_selecionado]

            # Embaralhar as perguntas
            random.shuffle(perguntas_nivel)

            # Iniciar o quiz
            pontuacao = 0
            for pergunta in perguntas_nivel:
                print("\nPergunta:", pergunta["pergunta"])
                resposta = input("Sua resposta: ")
                if resposta.lower() == pergunta["resposta"].lower():
                    print("Resposta correta!")
                    pontuacao += 1
                else:
                    print(f"Resposta incorreta. A resposta correta é: {pergunta['resposta']}")

            print(f"\nFim do quiz! Sua pontuação final é: {pontuacao}/{len(perguntas_nivel)}")
        else:
            print("Escolha de nível inválida.")
    else:
        print("Escolha de matéria inválida.")


# Executar o quiz
jogar_quiz()
# Dicionário de profissões com base nos resultados
profissoes = {
    "Estudante": (0, 2),
    "Assistente Administrativo": (3, 5),
    "Professor": (6, 8),
    "Engenheiro": (9, 11),
    "Médico": (12, 14),
    "Advogado": (15, 18),
}


# Função para determinar a profissão com base nos resultados
def determinar_profissao(acertos):
    for profissao, faixa in profissoes.items():
        if faixa[0] <= acertos <= faixa[1]:
            return profissao
    return "Não foi possível determinar uma profissão."


# Função principal do programa
def main():
    nome = input("Digite seu nome: ")
    print(f"Olá, {nome}! Bem-vindo ao Teste de Conhecimento.")

    # Simulação de resultados (substitua isso pela lógica real do jogo)
    acertos = 10  # Substitua pelo número real de acertos

    # Determine a profissão com base nos resultados
    profissao = determinar_profissao(acertos)

    print(f"Com base nos seus resultados, você se sairia melhor como {profissao}.")


if __name__ == "__main__":
    main()
