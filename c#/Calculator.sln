namespace Calculator
{
    public partial class Calculator : Form
    {
        string operand;
        double result = 0;
        int my_operator;

        public const int NONE = 0;
        public const int ADD = 1;
        public const int SUB = 2;
        public const int MUL = 3;
        public const int DIV = 4;
        public const int MOD = 5;

        public Calculator()
        {
            InitializeComponent();
            tb.Text = "";
            tb_result.Text = "";
        }

        private void AddNumber(string number)
        {
            operand += number;
            tb_result.Text = operand;
        }

        private void btn_1_Click(object sender, EventArgs e) => AddNumber("1");
        private void btn_2_Click(object sender, EventArgs e) => AddNumber("2");
        private void btn_3_Click(object sender, EventArgs e) => AddNumber("3");
        private void btn_4_Click(object sender, EventArgs e) => AddNumber("4");
        private void btn_5_Click(object sender, EventArgs e) => AddNumber("5");
        private void btn_6_Click(object sender, EventArgs e) => AddNumber("6");
        private void btn_7_Click(object sender, EventArgs e) => AddNumber("7");
        private void btn_8_Click(object sender, EventArgs e) => AddNumber("8");
        private void btn_9_Click(object sender, EventArgs e) => AddNumber("9");
        private void btn_0_Click(object sender, EventArgs e) => AddNumber("0");

        private void btn_dot_Click(object sender, EventArgs e) => AddNumber(".");

        private void PerformOperation(int operation, string symbol)
        {
            if (operand != "")
            {
                if (my_operator != NONE)
                {
                    double num_operand = Convert.ToDouble(operand);

                    switch (my_operator)
                    {
                        case ADD:
                            result += num_operand;
                            break;
                        case SUB:
                            result -= num_operand;
                            break;
                        case MUL:
                            result *= num_operand;
                            break;
                        case DIV:
                            result /= num_operand;
                            break;
                        case MOD:
                            result %= num_operand;
                            break;
                    }

                    tb.Text += operand + symbol;
                    tb_result.Text = result.ToString();
                    operand = "";
                    my_operator = operation;
                }
                else
                {
                    result = Convert.ToDouble(operand);
                    tb.Text += operand + symbol;
                    operand = "";
                    my_operator = operation;
                }
            }
        }

        private void btn_add_Click(object sender, EventArgs e) => PerformOperation(ADD, " + ");
        private void btn_sub_Click(object sender, EventArgs e) => PerformOperation(SUB, " - ");
        private void btn_mul_Click(object sender, EventArgs e) => PerformOperation(MUL, " × ");
        private void btn_div_Click(object sender, EventArgs e) => PerformOperation(DIV, " ÷ ");
        private void btn_remain_Click(object sender, EventArgs e) => PerformOperation(MOD, " % ");

        private void btn_result_Click(object sender, EventArgs e)
        {
            PerformOperation(NONE, " = ");
            my_operator = NONE;
        }


        private void btn_clear_Click(object sender, EventArgs e)
        {
            tb.Text = "";
            tb_result.Text = "";
            operand = "";
            result = 0;
            my_operator = NONE;
        }

        private void btn_delete_Click(object sender, EventArgs e)
        {
            if (operand.Length > 0)
            {
                operand = operand.Substring(0, operand.Length - 1);
                tb_result.Text = operand;
            }
        }

        private void btn_pm_Click(object sender, EventArgs e)
        {
            if (operand.Length > 0)
            {
                double temp = Convert.ToDouble(operand) * -1;
                operand = temp.ToString();
                tb_result.Text = operand;
            }
        }
    }
}
