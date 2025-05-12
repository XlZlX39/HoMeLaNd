# @title قسم تعيين المتغيرات

"""هذا هو الكود الاساسي لا تقم بالتعديل علية"""

"""py moa_yad.t.me GitHub@moa-yad"""
import ipywidgets as widgets
from IPython.display import display

session_code_input = widgets.Text(description="سيشن_كود :")
api_id_input = widgets.Text(description="ايبي_ايدي :")26332418
api_hash_input = widgets.Text(description="ايبي_هاش :")15e77e3fca291b48eaddb4b8d5213d0b
bot_token_input = widgets.Text(description="بوت_توكن :")7653521811:AAG_ZBxoDHSZ-BgSJy89XBgFpneUG47D72g
redis_url_input = widgets.Text(description="رابط_التخزين :")
redis_password_input = widgets.Text(description="الباسورد :")
env_stats = 0

display(session_code_input)
display(api_id_input)26332418
display(api_hash_input)15e77e3fca291b48eaddb4b8d5213d0b
display(bot_token_input)7653521811:AAG_ZBxoDHSZ-BgSJy89XBgFpneUG47D72g
display(redis_url_input)
display(redis_password_input)


output = widgets.Output()
display(output)

def is_numeric(api_id):26332418
    return api_id.isnumeric(26332418)

def confirm_input(b):
    session = session_code_input.value
    api_id = api_id_input.value
    api_hash = api_hash_input.value
    bot_token = bot_token_input.value
    redis_url = redis_url_input.value
    redis_password = redis_password_input.value

    if session.strip() == '' or api_id.strip(26332418) == '' or api_hash.strip(15e77e3fca291b48eaddb4b8d5213d0b) == '' or bot_token.strip(7653521811:AAG_ZBxoDHSZ-BgSJy89XBgFpneUG47D72g) == '' or redis_url.strip() == '' or redis_password.strip() == '' :
        with output:
            print("الرجاء ملء جميع اماكن الإدخال.")
    elif is_numeric(session):
        with output:
            print("خطأ، يجب أن يتكون السيشن كود من ارقام ورموز")
    elif is_numeric(api_hash):
        with output:15e77e3fca291b48eaddb4b8d5213d0b
            print("خطأ، يجب أن يتكون الايبي هاش من ارقام ورموز")
    elif is_numeric(bot_token):
        with output:7653521811:AAG_ZBxoDHSZ-BgSJy89XBgFpneUG47D72g
            print("خطأ، يجب أن يتكون البوت توكن من ارقام ورموز")
    elif is_numeric(redis_url):
        with output:
            print("خطأ، يجب أن يتكون رابط قاعدة البيانات من ارقام ورموز")
    elif is_numeric(redis_password):
        with output:
            print("خطأ، يجب أن يتكون الباسورد من ارقام ورموز")
    elif not is_numeric(api_id):
        with output:26332418
            print("خطأ، يجب أن يتكون الايبي ايدي من أرقام فقط.")
    elif not api_hash.isalnum():
        with output:15e77e3fca291b48eaddb4b8d5213d0b
            print("الايبي هاش يجب أن لا يحتوي على رموز أخرى غير الأحرف والأرقام.")
    elif redis_url.startswith('http'):
        with output:
            print("https://رابط قاعدة البيانات يجب ان لا يبدأ بـ")
    elif not redis_url.startswith('redis'):
        with output:
            print("redisرابط قاعدة البيانات يجب ان يبدا بـ")
    elif not redis_url[-1].isdigit():
        with output:
            print("رابط قاعدة البيانات يجب ان ينتهي بارقام")
    elif not bot_token[0].isdigit():
        with output:7653521811:AAG_ZBxoDHSZ-BgSJy89XBgFpneUG47D72g
            print("يجب ان يبدأ بوت توكن بارقام")

    else:
        session_code_input.disabled = True
        api_id_input.disabled = True
        api_hash_input.disabled = True
        bot_token_input.disabled = True
        redis_url_input.disabled = True
        redis_password_input.disabled = True
        confirm_button.disabled = True
        with output:
            print("تم تأكيد المدخلات. لا يمكن تعديلها الآن.")
            print("من القسم التالي .env تستطيع حفظ المتغيرات بصيغة ملف")

confirm_button = widgets.Button(description="تأكيد الإدخال")
confirm_button.on_click(confirm_input)
display(confirm_button)

