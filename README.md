# 👇🏻 YOUR CODE 👇🏻:


#연간 매출 계산
def get_yearly_revenue(monthly_revenue):
  return monthly_revenue * 12


#연간 비용 계산
def get_yearly_expenses(monthly_expenses):
  return monthly_expenses * 12


# 이익을 인자로 받아서, 이익이 100,000보다 크면 25% 세율을 적용하고, 크지 않으면 15% 세율을 적용해서 세금금액을 리턴하는 함수
def get_tax_amount(profit):
  if profit > 100000:
    return profit * 0.25
  else:
    return profit * 0.15


#세금금액. 세액공제율을 인자로 받아서, 공제할 금액을 리턴하는 함수
def apply_tax_credits(tax_amount, tax_credits):
  amount_to_discount = tax_amount * tax_credits
  return amount_to_discount


# BLUEPRINT | DONT EDIT

monthly_revenue = 5500000
monthly_expenses = 2700000
tax_credits = 0.01

yearly_revenue = get_yearly_revenue(monthly_revenue)
yearly_expenses = get_yearly_expenses(monthly_expenses)

profit = yearly_revenue - yearly_expenses

tax_amount = get_tax_amount(profit)

final_tax_amount = tax_amount - apply_tax_credits(tax_amount, tax_credits)

print(f"Your tax bill is: ${final_tax_amount}")
