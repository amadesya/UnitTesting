# UnitTesting

ИСПП-35
Фролова Мия, Луев Роман 

using TestingLib.Math;

namespace UnitTesting.amadesya
{
    public class Basic
    {
        private readonly BasicCalc _calculator;

        public Basic()
        {
            _calculator = new BasicCalc();
        }

        [Fact]
        public void SolveQuadraticEquation_ShouldReturnCorrectRoots()
        {
            (double?,double?) descriminant = _calculator.SolveQuadraticEquation(1.0, 2.0, -3.0);
            Assert.Equal(descriminant, descriminant);
        }

        [Theory]
        [InlineData(2.0, 3.0, -5.0, 1.0, -2.5)]
        public void SolveQuadraticEquation_Theory(double a, double b, double c, double? expectedResult1, double? expectedResult2)
        {
            var discriminant = _calculator.SolveQuadraticEquation(a, b, c);
            Assert.Equal(expectedResult1, discriminant.Item1);
            Assert.Equal(expectedResult2, discriminant.Item2);
        }

        [Theory]
        [InlineData(2.0, 3.0, -5.0, 1.0, -2.5)]
        public void SolveQuadraticEquation_Exeption(double a, double b, double c, double? expectedResult1, double? expectedResult2)
        {

        }
    }
}

