let getRandomIntegerMatrix = function (stringNumber, columnNumber, maxInteger) {
    let matrix = [];

    for (let i = 0; i < stringNumber; i++) {
        let string = [];

        for (let j = 0; j < columnNumber; j++) {
            string[j] = Math.floor(Math.random() * maxInteger) + 1;
        }

    	matrix[i] = string;
    }

    return matrix;
}

let matrix = getRandomIntegerMatrix(3, 3, 4);

for (let i = 0; i < matrix.length; i++) {
	console.log(matrix[i]);	
}


let findMatrixDeterminant = function (squareMatrix) {
    let sum = 0;
                                                                   //берем 1ю строку и получаем миноры вычеркиванием строк и столбцов
    for (let i = 0; i < squareMatrix.length; i++) {                //перебираем елементы первой строки матрицы 
        let minor = [];

        for (let j = 1; j < squareMatrix.length; j++) {             // записываем минор i-го элемента 1 строки / перебираем строчные индексы кроме первой строки
            let string = [];

            for (let k = 0; k < squareMatrix.length; k++) {         // столбцовые индексы
                if (k !== i) {
                    string.push(squareMatrix[j][k]);                //j-1-ая строка минора
                }
            }

            minor.push(string);                                     // записываем строку в минор
        }

        let  minorClone = minor.slice();
        
        let cofactor = 1;
        if (i % 2 === 0) {
        	cofactor = -1;
        }

        if (minorClone.length === 1) {
        	sum += cofactor * squareMatrix[0][i] * minorClone[0];
        } else {
        	sum += cofactor * squareMatrix[0][i] * findMatrixDeterminant(minorClone); // рекурсия, надо вычислить минор
        }
    }

    return sum;
};

findMatrixDeterminant(matrix);
