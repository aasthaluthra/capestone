# capestone
select cu.customer_id, cu.first_name, cu.last_name,
cu.email, cu.address_id, 
ru.rental_id, ru.rental_date, ru.inventory_id,
ru.return_date, ru.staff_id, 
inv.film_id, fi.title, fi.description,
fi.release_year, fi.language_id, fi.rental_duration, 
fi.rental_rate, fi.length, 
fi.rating, fi.last_update, fi.special_features, fi.fulltext,
pay.payment_id, pay.amount, pay.payment_date,
ci.city_id, ci.city, cou.country_id, cou.country
from customer cu
inner join rental ru
on cu.customer_id=ru.customer_id
inner join inventory inv
on ru.inventory_id=inv.inventory_id
inner join film fi
on inv.film_id=fi.film_id
inner join payment pay
on ru.rental_id=pay.rental_id
inner join address ad
on cu.address_id=ad.address_id
inner join city ci
on ad.city_id=ci.city_id
inner join country cou
on ci.country_id=cou.country_id
order by customer_id;
