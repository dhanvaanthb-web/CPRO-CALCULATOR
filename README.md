#include <stdio.h>
#include <string.h>
#include <stdbool.h>
#include <math.h>
#include <ctype.h>
void uppercase(char str[])
{
    int i;
    for (i = 0; str[i] != '\0'; i++)
    {
        str[i] = toupper((unsigned char)str[i]);
    }
}
int main()
{
    int result, next, A[3][3], B[3][3], C[3][3],i,j,k;
    char op,Choice[20],matrixc[15],modec[10];
    printf("Enter Normal or Mode: ");
    scanf("%19s", Choice);
    uppercase(Choice);
    if (strcmp(Choice, "NORMAL") == 0)
    {
        printf("Enter a first number: ");
        scanf("%d", &result);
        while (true)
            {
                printf("Enter a operator to calculate: ");
                scanf(" %c", &op);
                if (op == '=')
                {
                    printf("Result: %d",result);
                    break;
                }
                printf("Enter a second number: ");
                scanf("%d", &next);
                switch(op)
                {
                    case '+':result=result+next;break;
                    case '-':result=result-next;break;
                    case '*':result=result*next;break;
                    case '/':
                        if (next != 0)
                            result = result / next;
                    else
                        printf("Cannot divide by zero!\n");break;
                    case '%':
                        if (next != 0)
                            result = result % next;
                    else
                        printf("Cannot divide by zero!\n");break;
                    default:printf("Invalid Operator");
                }
                printf("Result: %d\n",result);
            }
    }
    else 
    {
        printf("Enter 3x3Matrix or 2x2Matrix or sin or cos or tan: ");
        scanf(" %9s", modec);
        uppercase(modec);
        if (strcmp(modec, "3X3MATRIX")==0)
        {
            printf("Enter Add or Subtract or Multiply: ");
            scanf(" %14s", matrixc);
            uppercase(matrixc);
            if (strcmp(matrixc, "ADD")==0)
            {
                for (i=1;i<4;i++)
                    for (j=1;j<4;j++)
                    {
                        printf("Enter a number to A[%d][%d], B[%d][%d]: ",i,j,i,j);
                        scanf("%d %d",&A[i][j],&B[i][j]);
                        C[i][j]= A[i][j] + B[i][j];
                    }
                printf("Result Matrix:\n");
                for (i=1;i<4;i++)
                {
                    for (j=1;j<4;j++)
                    {
                        printf("%5d",C[i][j]);
                    }
                printf("\n");
                }
            }
            else if (strcmp(matrixc, "SUBTRACT")==0)
            {
                for (i=1;i<4;i++)
                    for (j=1;j<4;j++)
                    {
                        printf("Enter a number to A[%d][%d], B[%d][%d]: ",i,j,i,j);
                        scanf("%d %d",&A[i][j], &B[i][j]);
                        C[i][j]= A[i][j] - B[i][j];
                    }
                printf("Result Matrix:\n");
                for (i=1;i<4;i++)
                {
                    for (j=1;j<4;j++)
                    {
                        printf("%5d",C[i][j]);
                    }
                printf("\n");
                }
            }
            else
            {
                for (i=1;i<4;i++)
                {
                    for (j=1; j<4;j++)
                    {
                        printf("Enter a number to A[%d][%d] B[%d][%d]: ", i,j,i,j);
                        scanf("%d %d", &A[i][j], &B[i][j]);
                    }
                }
                for (i=1;i<4;i++)
                {
                    for (j=1; j<4;j++)
                    {
                        C[i][j] = 0;
                        for (k=1;k<4;k++)
                        {
                            C[i][j] += A[i][k] * B[k][j];
                        }
                    }
                }
                printf("Result Matrix:\n");
                for (i=1;i<4;i++)
                {
                    for (j=1; j<4;j++)
                    {
                        printf("%5d", C[i][j]);
                    }
                    printf("\n");
                }
            }
        }
        else if (strcmp(modec, "2X2MATRIX")==0)
        {
            printf("Enter Add or Subtract or Multiply: ");
            scanf(" %14s", matrixc);
            if (strcmp(matrixc, "Add")==0)
            {
                for (i=1;i<3;i++)
                    for (j=1;j<3;j++)
                    {
                        printf("Enter a number to A[%d][%d], B[%d][%d]: ",i,j,i,j);
                        scanf("%d %d",&A[i][j],&B[i][j]);
                        C[i][j]= A[i][j] + B[i][j];
                    }
                printf("Result Matrix:\n");
                for (i=1;i<3;i++)
                {
                    for (j=1;j<3;j++)
                    {
                        printf("%5d",C[i][j]);
                    }
                printf("\n");
                }
            }
            else if (strcmp(matrixc, "Subtract")==0)
            {
                for (i=1;i<3;i++)
                    for (j=1;j<3;j++)
                    {
                        printf("Enter a number to A[%d][%d], B[%d][%d]: ",i,j,i,j);
                        scanf("%d %d",&A[i][j], &B[i][j]);
                        C[i][j]= A[i][j] - B[i][j];
                    }
                printf("Result Matrix:\n");
                for (i=1;i<3;i++)
                {
                    for (j=1;j<3;j++)
                    {
                        printf("%5d",C[i][j]);
                    }
                printf("\n");
                }
            }
            else
            {
                for (i=1;i<3;i++)
                {
                    for (j=1; j<3;j++)
                    {
                        printf("Enter a number to A[%d][%d] B[%d][%d]: ", i,j,i,j);
                        scanf("%d %d", &A[i][j], &B[i][j]);
                    }
                }
                for (i=1;i<3;i++)
                {
                    for (j=1; j<3;j++)
                    {
                        C[i][j] = 0;
                        for (k=1;k<3;k++)
                        {
                            C[i][j] += A[i][k] * B[k][j];
                        }
                    }
                }
                printf("Result Matrix:\n");
                for (i=1;i<3;i++)
                {
                    for (j=1; j<3;j++)
                    {
                        printf("%5d", C[i][j]);
                    }
                    printf("\n");
                }
            }
        }
        else if (strcmp(modec, "SIN") == 0)
        {
            double angle, result;
            printf("Enter angle in degrees: ");
            scanf("%lf", &angle);
            result = sin(angle * 3.141592653589793 / 180.0);
            printf("sin(%.2lf) = %.4lf\n", angle, result);
        }
        else if (strcmp(modec, "COS") == 0)
        {
            double angle, result;
            printf("Enter angle in degrees: ");
            scanf("%lf", &angle);
            result = cos(angle * 3.141592653589793 / 180.0);
            printf("cos(%.2lf) = %.4lf\n", angle, result);
        }
        else if (strcmp(modec, "TAN") == 0)
        {
            double angle, result;
            printf("Enter angle in degrees: ");
            scanf("%lf", &angle);
            result = tan(angle * 3.141592653589793 / 180.0);
            printf("tan(%.2lf) = %.4lf\n", angle, result);
        }
    }
    return 0;
}
