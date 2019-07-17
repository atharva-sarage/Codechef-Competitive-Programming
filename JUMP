/******************************************
*    AUTHOR:         Atharva Sarage       *
*    INSTITUITION:   IIT HYDERABAD        *
******************************************/
#include<bits/stdc++.h>
#warning Check Max_Limit,Overflows
using namespace std;
# define IOS ios::sync_with_stdio(0);cin.tie(0);cout.tie(0);
# define ff first
# define ss second
# define pb push_back
# define mod 1000000007
# define ll long long 
# define db double
# define mx2 100005
# define mx 300005
struct Line {
	mutable ll k, m, p;
	bool operator<(const Line& o) const { return k < o.k; }
	bool operator<(ll x) const { return p < x; }
};

struct LineContainer : multiset<Line, less<>> {
	// (for doubles, use inf = 1/.0, div(a,b) = a/b)
	const ll inf = LLONG_MAX;
	ll div(ll a, ll b) { // floored division
		return a / b - ((a ^ b) < 0 && a % b); }
	bool isect(iterator x, iterator y) {
		if (y == end()) { x->p = inf; return false; }
		if (x->k == y->k) x->p = x->m > y->m ? inf : -inf;
		else x->p = div(y->m - x->m, x->k - y->k);
		return x->p >= y->p;
	}
	void add(ll k, ll m) {
		auto z = insert({k, m, 0}), y = z++, x = y;
		while (isect(y, z)) z = erase(z);
		if (x != begin() && isect(--x, y)) isect(x, y = erase(y));
		while ((y = x) != begin() && (--x)->p >= y->p)
			isect(x, erase(y));
	}
	ll query(ll x) {
		assert(!empty());
		auto l = *lower_bound(x);
		return l.k * x + l.m;
	}
};
LineContainer BIT[mx];
ll a[mx],p[mx],h[mx],dp[mx];
void update(ll i,Line l)
{
	while(i<=mx)
	{
		BIT[i].add(-l.k,-l.m);
		i+=(i&-i);
	}
}
ll query(ll i,ll x)
{
	ll min1=LLONG_MAX;
	while(i>0)
	{
		if(!BIT[i].empty())
		min1=min(min1,-BIT[i].query(x));
		i-=(i&-i);
	}
	return min1;
}
int main()
{
	IOS;
	ll n;
	cin>>n;
	for(ll i=1;i<=n;i++)
		cin>>p[i];
	for(ll i=1;i<=n;i++)
		cin>>a[i];
	for(ll i=1;i<=n;i++)
		cin>>h[i];
	dp[1]=a[1];
	for(ll i=1;i<=n;i++)
	{
		if(i!=1)
			dp[i]=a[i]+h[i]*h[i]+query(p[i],h[i]);
		Line temp={-2*h[i],dp[i]+h[i]*h[i]};
		update(p[i],temp);
	}
	cout<<dp[n]<<endl;
}